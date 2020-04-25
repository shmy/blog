---
title: nginx在docker中使用环境变量
date: 2020-04-25 10:07:32
categories: ["backend", "summaries"]
tags: ["nginx", "docker"]
---

## 前言

> 在前后端分离的项目上，目前主流的前端部署方案是，前端单独打包一个`docker`镜像，用`nginx`来做`http`访问和后端服务代理，这样既可以解决前后端分离的跨域问题，也可以隐藏真实的后端地址；

> 一个典型的`nginx.conf`如下

```conf
server {
  listen 80;
  location / {
    root   /usr/share/nginx/html;
    index  index.html index.htm;
    try_files $uri $uri/ /index.html;
  }
  location /api/ {
    proxy_pass http://127.0.0.1:8080;
    proxy_set_header Host $host;
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
  }
}

```

> 其中`http://127.0.0.1:8080`为后端地址，当访问前端的`url`，如果以`/api`开头的路径，将会被代理到`http://127.0.0.1:8080`

<!-- more -->

> Dockerfile

```dockerfile
FROM nginx:stable-alpine
COPY dist /usr/share/nginx/html
RUN rm /etc/nginx/conf.d/default.conf
COPY nginx.conf /etc/nginx/conf.d
EXPOSE 80
ENTRYPOINT nginx -g 'daemon off;'

```



## 需要动态切换代理的目标地址

> 目前我们的项目部署有多套环境，有的后端的地址和端口部署后并不一致，需要前端的容器在启动时，能够动态设置后端的地址。

> 我们期望是能够通过启动容器时设置环境变量来实现，如：

> 首先在 `Dockerfile` 中设置默认的环境变量 `BACKEND_URL=http://127.0.0.1:8080`

```bash
FROM nginx:stable-alpine
COPY dist /usr/share/nginx/html
RUN rm /etc/nginx/conf.d/default.conf
COPY nginx.conf /etc/nginx/conf.d
ENV BACKEND_URL http://127.0.0.1:8080
EXPOSE 80
ENTRYPOINT nginx -g 'daemon off;'
```

> 我们期望能够这样设置和启动：

```bash
docker run --name our-frontend-service -d -e BACKEND_URL=http://127.0.0.1:4200 our-frontend
```

> 接着我们需要设置`nginx.conf`配置文件， 那么问题来了，`ngxin`不支持在在配置文件中读取系统环境变量，经过一番`Google`，发现了`Docker`官方推荐使用`envsubst`来实现，我们接着看看：

## envsubst

> `envsubst`是一个环境变量替换的命令，它可以帮我们替换指定的文件内的环境变量，我们来试试：

> 新建一个测试文件`test.template`

```txt
I'm ${NAME}, Welcome to my ${PLACE}
```

> 执行一下：

```bash
/etc/nginx/conf.d # envsubst < test.template
I'm , Welcome to my
/etc/nginx/conf.d #
```

> 可以看到 输出的内容里， `${NAME}`和`${PLACE}`变成了空，这说明当前系统环境变量里不存在这些变量，我们添加一下再试试：

```bash
/etc/nginx/conf.d # export NAME=student
/etc/nginx/conf.d # export PLACE=school
/etc/nginx/conf.d # envsubst < test.template
I'm student, Welcome to my school
/etc/nginx/conf.d #

```

> 可以看到，`envsubst`对文件内容的环境变量部分进行了替换，并输出。

> 接着咱们把输出的内容重新保存成一个文件看看：

```bash
/etc/nginx/conf.d # envsubst < test.template > test.txt
/etc/nginx/conf.d # cat test.txt
#I'm student, Welcome to my school
/etc/nginx/conf.d #
```

> 这样我们就可以把替换后的内容保存成新的文件

## 改造

> 接下来我们来改造我们的`nginx.conf`，我们希望在容器启动时，读取环境变量，利用`envsubst`替换`nginx.conf`中的变量，然后生成新的`nginx`配置文件后再启动`nginx`。

+ 把 原来的`nginx.conf`重名为`nginx.template`，并将`proxy_pass`的值设置为环境变量：

```conf
server {
  listen 80;
  location / {
    root   /usr/share/nginx/html;
    index  index.html index.htm;
    try_files $uri $uri/ /index.html;
  }
  location /api/ {
    proxy_pass ${BACKEND_URL};
    proxy_set_header Host $host;
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
  }
}
```


+ 修改`Dockerfile`，将`ngxin.template` 拷贝到 `/etc/nginx/conf.d`， 并设置`WORKDIR`为`/etc/nginx/conf.d`

```dock
FROM nginx:stable-alpine
COPY dist /usr/share/nginx/html
RUN rm /etc/nginx/conf.d/default.conf
COPY nginx.template /etc/nginx/conf.d
ENV BACKEND_URL http://127.0.0.1:8080
EXPOSE 80
WORKDIR /etc/nginx/conf.d
ENTRYPOINT envsubst < nginx.template > nginx.conf && nginx -g 'daemon off;'

```

> 我们运行看看：

```
docker run --name our-frontend-service -d -e BACKEND_URL=http://127.0.0.1:4200 our-frontend
```

> 结果发现启动报错：

```bash
2020/04/25 02:45:44 [emerg] 1#1: invalid number of arguments in "proxy_set_header" directive in /etc/nginx/conf.d/nginx.conf:10
nginx: [emerg] invalid number of arguments in "proxy_set_header" directive in /etc/nginx/conf.d/nginx.conf:10
```

> 我们来`DEBUG`一下

> 修改`Dockerfile`，我们在保存新的文件后看看内容

```doc
ENTRYPOINT envsubst < nginx.template > nginx.conf && cat nginx.conf && nginx -g 'daemon off;'
```

```conf
server {
  listen 80;
  location / {
    root   /usr/share/nginx/html;
    index  index.html index.htm;
    try_files  / /index.html;
  }
  location /api/ {
    proxy_pass http://127.0.0.1:4200;
    proxy_set_header Host ;
    proxy_set_header X-Real-IP ;
    proxy_set_header X-Forwarded-For ;
  }
}
```

> 哦，看来`envsubst`把`$url`, `$host`, `$remote_addr`, `$proxy_add_x_forwarded_for`都认为是环境变量进行了替换😭

## 修复

> 经过查阅，发现`envsubst`可以指定需要替换的变量

```dockerfile
ENTRYPOINT envsubst '${BACKEND_URL}' < nginx.template > nginx.conf && cat nginx.conf && nginx -g 'daemon off;'
```

> 多个变量使用空格隔开即可 `envsubst '${BACKEND_URL} ${OTHER_VAR1} ${OTHER_VAR2}' ...`

```bash
server {
  listen 80;
  location / {
    root   /usr/share/nginx/html;
    index  index.html index.htm;
    try_files $uri $uri/ /index.html;
  }
  location /api/ {
    proxy_pass http://127.0.0.1:4200;
    proxy_set_header Host $host;
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
  }
}
```

> 完美， 大功告成！
