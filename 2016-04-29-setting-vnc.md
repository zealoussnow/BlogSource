---
title: Linux VNC服务配置
date: 2016-04-29 18:07:18
categories:
- 程序设计
tags:
- Linux基础
permalink: setting-vnc
---

### CentOS-6.5安装和配置VNC服务

1.下载tigervnc的客户端和服务端程序

```shell
# yum install tigervnc-server tigervnc
```

<!-- more -->

2.为普通用户设置vnc服务

编辑/etc/sysconfig/vncservers，加入

```shell
VNCSERVERS="8:test"
VNCSERVERARGS[8]="-geometry 1400x900 -nolisten tcp"
```

添加的用户test必须是系统中已经存在的用户。

3.为test设置vnc的登录密码

切换到普通用户上，使用vncpasswd设置密码

4.启动vnc服务

    ```
    service vncserver start
    ```

### 参考资料

[CentOS-6.5安装配置tigervnc](http://blog.sina.com.cn/s/blog_6cf180d10102v07j.html)
[VNC服务全面设置](http://wenku.baidu.com/link?url=JCaAqi004QuvYXbBRvXC1qUZYvjnXHPF8Mx33wPmsUKsXXHl_tQa8npKMwvSYMYhewAv2cTU38PbF0dv3m-4uEiFfH7qFvEQ3AkhPmPfQlu)

