---
title: 私有部署git服务之GOGS
date: 2020-04-16 14:06:22
categories: ["devOps", "summaries"]
tags: ["git"]

---

## 什么是 Gogs?

> Gogs 是一款极易搭建的自助 Git 服务。
>
> 👂我们平常都是使用 `Github`, 等免费的托管平台，但是对于某些视源代码如生命的商业公司来说，既不想公开源代码，又舍不得给GitHub交保护费，那就只能自己搭建一台Git服务器作为私有仓库使用。

<!-- more -->

## 开发目的

> Gogs 的目标是打造一个最简单、最快速和最轻松的方式搭建自助 Git 服务。使用 Go 语言开发使得 Gogs 能够通过独立的二进制分发，并且支持 Go 语言支持的 **所有平台**，包括 Linux、Mac OS X、Windows 以及 ARM 平台。

+ 官网：https://gogs.io

+ 项目地址：https://github.com/gogs/gogs

## 安装

> 使用docker 一键安装
>
> ⚠️ 如果使用树莓派等`ARM`架构的设置，使用 `gogs/gogs-rpi` 这个镜像

```bash
$ mkdir gogs
$ cd gogs
$ docker run -d --name=gogs -p 10022:22 -p 10080:3000 -v $(pwd):/data gogs/gogs
Unable to find image 'gogs/gogs:latest' locally
latest: Pulling from gogs/gogs
aad63a933944: Already exists
b0ad6e0fd7a4: Pull complete
33bdfa6ba679: Pull complete
23daa3948d44: Pull complete
7dfae03b6536: Pull complete
54b2aac72740: Pull complete
bca016e1cd26: Pull complete
40aa0bd71838: Pull complete
Digest: sha256:51c6e38c618b991307462348314d5b18baf7c85c946d4be58ddbae86e97d6dc7
Status: Downloaded newer image for gogs/gogs:latest
c8aa33cfd796b3f8f856e57444e022ab392fc82c3a4ad895ff6c470474d8c13d
```

> 接下来浏览器打开 http://localhost:10080，初次使用会跳转到 http://localhost:10080/install 页面进行安装设置，Gogs内置许多语言，你可以在页面右下角选择语言：

![ZX4Y6nhr8lfyAuJ](https://i.loli.net/2020/04/16/ZX4Y6nhr8lfyAuJ.png)

> Dogs 支持`PostgreSQL`, `MySQL`,`MSSQL`和`SQLite3`作为存储引擎

![bX1GyhMAslgpqTu](https://i.loli.net/2020/04/16/bX1GyhMAslgpqTu.png)

> 选择适合你的存储方案，设置即可。

> 如果没有在刚刚安装时设置管理员信息，那么在注册第一个用户时，会被添加为管理员。

![TZvN8FlGOX2thMz](https://i.loli.net/2020/04/16/TZvN8FlGOX2thMz.png)

> 以下是安装完毕后的主页。由于我这里docker端口做了映射，所以要重置一下 应用URL到 http://localhost:10080/
>
> 
>
> 如果已经绑定了域名，配置`SSH`端口之类的，参考官网的配置方法：https://gogs.io/docs/installation/configuration_and_run

![jgW32VNAMdvtX1w](https://i.loli.net/2020/04/16/jgW32VNAMdvtX1w.png)

> 登录后

![AM8js2Z7npiQXWx](https://i.loli.net/2020/04/16/AM8js2Z7npiQXWx.png)

> 创建仓库

![IY9AGza5njNK7qe](https://i.loli.net/2020/04/16/IY9AGza5njNK7qe.png)

