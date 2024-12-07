---
title: CloudTorrent
published: 2023-09-09
description: Centos 8 物理网卡开关机
image: ./cover.jpg
tags: [CentOS, linux, cloudtorrent]
category: Back-end
draft: false
---

说明

-p 后面是监听端口；

-a 后面是用户:密码 ;

-c后面cloud-torrent的配置文件(后面会单独介绍该文件)；

-l 是日志输出

>> 日志输出到目录文件 **/var/log/cloud-torrent.log**

## 配置文件说明

```json
{

  "AutoStart": true, #自动启动下载

  "DisableEncryption": false, #禁用加密

  "DownloadDirectory": "/Paimon/PaimonHDD/Anime",#文件下载到的目录

  "EnableUpload": false, #是否上传

  "EnableSeeding": false,#是否启用种子

  "IncomingPort": 8100 #输入端口

}
```