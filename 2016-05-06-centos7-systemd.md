---
title: CentOS7的使用 —— systemd
date: 2016-05-06 10:00:39
categories: 程序设计
tags: Linux基础
permalink: centos7-systemd
---

检视和控制systemd的主要命令是systemctl，该命令可用于查看系统状态和管理系统及服务。

在systemctl参数中添加-H `<username>`@`<host>`，可以实现对其他机器的远程控制，该过程使用SSH连接。

<!-- more -->

systemadm是systemd的官方图形前端，[官方软件仓库](https://wiki.archlinux.org/index.php/Official_repositories)提供了稳定版的[systemd-ui](https://www.archlinux.org/packages/?name=systemd-ui)

## 分析系统状态

### 输出激活的单元
```
# systemctl 或者 systemctl list-units
```
### 输出运行失败的单元
```
# systemctl --failed
```

### 查看所有已安装的服务
```
systemctl list-unit-files
```
所有可用单元文件存放在`/usr/lib/systemd/system`和`/etc/systemd/system`目录(后者优先级更高)。

## 使用单元

### 立即激活单元
```
# systemctl  start <unit>
```

### 立即停止单元
```
# systemctl stop <unit>
```

### 重启单元
```
# systemctl restart <unit>
```

### 重新加载配置
```
# systemctl reload <unit>
```

### 输出单元运行状态
```
# systemctl status <unit>
```

### 检查单元是否配置为自动启动
```
# systemctl is-enabled <unit>
```

### 开机自动激活单元
```
# systemctl enable <unit>
```

### 取消开机自动激活单元
```
# systemctl disable <unit>
```

### 禁用一个单元（禁用后，间接启动也是不可能的）
```
# systemctl  mask <unit>
```

### 取消禁用一个单元
```
# systemctl unmask <unit>
```

### 重新载入systemd
```
# systemctl daemon-reload
```

###  显示单元的手册页（必须由单元文件提供）
```
# systemctl help <unit>
```

##  电源管理
安装[polkit(https://wiki.archlinux.org/index.php/Polkit)]后才可以让一般用户使用电源管理

```
systemctl reboot(重启) | poweroff(退出系统并停止电源) | suspend(待机) | hibernate(休眠) | hybrid-sleep(混合休眠模式)
```

编写单元文件等内容请看参考。。。

### 参考

[systemd详解](http://xiaoli110.blog.51cto.com/1724/1629533)
[Archlinux Wiki, systemd](https://wiki.archlinux.org/index.php/Systemd_(%E7%AE%80%E4%BD%93%E4%B8%AD%E6%96%87))
[systemctl命令完全指南](https://linux.cn/article-5926-1.html)