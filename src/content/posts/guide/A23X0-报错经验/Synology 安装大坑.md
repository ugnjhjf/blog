---
title: Synology 安装大坑
published: 2021-04-04
description: ""
tags: [Synology, server, VMDK, linux]
category: Back-end
draft: false
---
ESXI - 安装群辉 

2021年4月4日23:55:42 

装了七个小时，设置都没问题，问题出在 

1. 上传时将<font color="#ff0000">synoboot.vmdk</font>上传至 服务器 文件夹内，不然重启后会被刷掉，无法进入 
2. 硬盘需要设置为 独立-持久 
3. 网卡必须为 E1000e 
4. 删除光盘iso,SCSI控制器 
5. 用SATA控制器