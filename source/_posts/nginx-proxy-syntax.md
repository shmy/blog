---
title: nginx proxy 地址的问题
date: 2020-04-16 13:53:44
categories: ["backend", "summaries"]
tags: ["nginx"]
---
### 第一种：
```conf
location /proxy/ {
    proxy_pass http://127.0.0.1/;
}
```
> 代理到URL：http://127.0.0.1/test.html

<!-- more -->


### 第二种：
```conf
location /proxy/ {
    proxy_pass http://127.0.0.1;  #少/
}
```
> 代理到URL：http://127.0.0.1/proxy/test.html


### 第三种：
```conf
location /proxy/ {
    proxy_pass http://127.0.0.1/aaa/;
}
```
> 代理到URL：http://127.0.0.1/aaa/test.html


### 第四种（相对于第三种，最后少一个 / ）
```conf
location /proxy/ {
    proxy_pass http://127.0.0.1/aaa;
}
```
> 代理到URL：http://127.0.0.1/aaatest.html
