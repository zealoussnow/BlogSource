---
title: C++程序构建工具
date: 2016-04-29 17:40:45
categories:
- 程序设计
tags:
- C++
permalink: build-tools
---

[depot_tools](https://chromium.googlesource.com/chromium/tools/depot_tools/+/master)

[gyp](https://chromium.googlesource.com/experimental/external/gyp/+/master)

### Linux

```shell
export GYP_GENERATORS=make,ninja
make
ninja -C out/Default
```

<!-- more -->

### Windows

```shell
set GYP_MSVS_VERSION=2015
set GYP_GENERATORS=msvs,ninja
```

gyp支持的本地构建工具有：
cmake,eclipse,make,msvs,ninja,xcode

在windows下让cmake生成makefile必须用gnu makefile。

### 参考

[Hello GYP](http://erikge.com/articles/HelloGyp/)
[Hello Ninja](http://erikge.com/articles/HelloNinja/)
[Hello CMake](http://erikge.com/articles/HelloCMake/)
