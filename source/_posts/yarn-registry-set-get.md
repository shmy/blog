---
title: yarn替换仓库源到淘宝镜像
date: 2016-12-16 12:01:14
categories: ["frontend", "summaries"]
tags: ["node", "yarn"]
---
### 什么是Yarn？
> Yarn 是 Facebook, Google, Exponent 和 Tilde 开发的一款新的 JavaScript 包管理工具。就像我们可以从官方文档了解那样，它的目的是解决这些团队使用 npm 面临的少数问题，即：  
+ 安装的时候无法保证速度/一致性
+ 安全问题，因为 npm 安装时允许运行代码

### 修改为淘宝镜像
#### 获取yarn当前配置源地址  
```bash
$ yarn config get registry
# -> https://registry.yarnpkg.com
```
### 设置为淘宝镜像
```bash
$ yarn config set registry https://registry.npm.taobao.org
# -> yarn config v0.19.1
# -> success Set "registry" to "https://registry.npm.taobao.org".
# -> Done in 0.08s.
```
