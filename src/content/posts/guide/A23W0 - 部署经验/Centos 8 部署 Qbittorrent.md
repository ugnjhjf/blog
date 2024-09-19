---
title: Centos 8 部署 Qbittorrent
published: 2024-08-20
description: ''
image: ''
tags: ['服务器','后端','linux','qbittorrent']
category: '后端'
draft: false 
lang: ''
---

1.     安装qBittorrent

```sh
 sudo yum install qbittorrent-nox.x86_64
```

2.     创建systemctl脚本

```sh
sudo vi /usr/lib/systemd/system/qbittorrent.service
```

3.     在上面的文件中输入下列内容

```sh
[Unit]

Description=qbittorrent torrent server

[Service]

User=root

ExecStart=/usr/bin/qbittorrent-nox

Restart=on-abort

[Install]

WantedBy=multi-user.target
```

4.     启动服务

```sh
systemctl enable qbittorrent.service

```

5.     启动软件

```sh
qbittorrent-nox
```

6.     Ctrl+C结束进程

7.     后台运行

```shsystemctl start qbittorrent.service


systemctl start qbittorrent.service #开启qb

systemctl stop qbittorrent.service #关闭qb

systemctl restart qbittorrent.service #重启qb

```

[http://ip](http://ip):8080 进入网页管理界面

配置文件位置:

```sh

cd ~/.config/qBittorrent/qBittorrent.conf
```

卸载软件包:

```sh
yum remove
```

查询所有安装的软件包

```sh
yum list installed
```

移除QB

```sh
yum remove qbittorrent-nox-1:4.2.5-2.el8.x86_64
```
