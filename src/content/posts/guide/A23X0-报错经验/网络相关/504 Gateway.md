---
title: Nginx 504 Gateway
published: 2023-09-09
description: Nginx 504 Gateway
image: ./cover.jpg
tags: [CentOS, linux, nginx]
category: Back-end
draft: false
---
#报错经验 #网络 #反向代理 #nginx #centos #linux 
问题描述：

NginxS服务器 DDNS正常，反代正常，但是无法访问StarStone 服务器

问题成因：

想要设置Metric地址，但是路由部分设置错误了

解决方案：

将路由部分改为“自动”

![[Pasted image 20240405190639.png]]