---
title: Jellyfin和Qbittorrent权限不足的问题 及 系统安全性加固
published: 2024-01-16
description: ''
image: ''
tags: ['Jellyfin','qbittorrent','linux','网络','权限','网络安全','debug']
category: '后端'
draft: false 
lang: ''
---


# 报错经验 #网络安全 #网络 #权限 #Jellyfin #qbittorrent

问题分析：Qbittorrent下载到的文件属于root,Jellyfin无法删除或者读取视频文件

解决方法：Qbittorrent的启动用户为root，更改为其他用户，同时将jellyfin和Qbittorrent放到同一个用户组里面，使用775权限

服务文件可以在下面目录找到

```shell
vim /etc/systemd/system/

vim /usr/lib/systemd/system/qbittorrent.service
```

```shell
[Unit]
Description=qbittorrent torrent server

[Service]
User=root
ExecStart=/usr/bin/qbittorrent-nox
Restart=on-abort

[Install]
WantedBy=multi-user.target
~                                                                               
~                             
```

更改user为jellyfin

刷新系统服务

```shell
systemctl daemon-reload
```

重启qbittorrent

```shell
systemctl restart qbittorrent.service 
```

赋予权限

```shell
chmod -R 775 文件夹名
```
