---
title: Centos 8 防火墙和任务管理器
published: 2024-08-20
description: ''
image: ''
tags: ['服务器','后端','linux','防火墙','网络安全','网络']
category: '后端'
draft: false 
lang: ''
---


# centos #linux #后端  #防火墙 #网络 #网络安全

### 防火墙

查看开放的端口列表

```sh
firewall-cmd --zone=public --list-ports
```

开放防火墙端口3306

```sh

firewall-cmd --zone=public --add-port=3306/tcp --permanent
```

查看防火墙某个端口是否开放

```sh
firewall-cmd --query-port=3306/tcp
```

# 任务管理器

查看任务管理器

```sh
ps aux --sort -rss

top
```

杀死进程: kill + PID

```sh
kill PID
```

杀死程序下所有进程

```sh
killall -9 java
```

-2 终止(Ctrl+c)

-9强制终止！！！
