---
title: Electron快速入门
date: 2016-04-28 11:36:43
categories:
- Nodejs
tags:
- Electron
permalink: electron-quick-start
---

### Electron简介

Electron是一种可以使用网页技术来开发跨平台桌面应用的解决方案，用html，css和js就可以写桌面应用。

<!-- more -->

### 安装cnpm

安装好了nodejs和npm之后，为了方便在国内下载npm包，可以使用淘宝的npm镜像

首先安装cnpm

```shell
npm install -g cnpm --registry=https://registry.npm.taobao.org
```

### 安装electron

```shell
cnpm install electron-prebuilt -g
```

### 运行官方示例electron-quick-start

```shell
git clone https://github.com/electron/electron-quick-start
cd electron-quick-start
npm install
npm start
```

运行结果如图所示：

<div align="center">
![运行结果](electron-quick-start/electron-quick-start.jpg)
</div>
