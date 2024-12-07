---
title: qbittorrent 切换用户之后无法登入
published: 2023-09-09
description: ""
tags: [Qbittorrent, server, network, linux]
category: Back-end
draft: false
---
#后端 #权限  #报错经验 #qbittorrent 
问题描述：服务qbittorrent从root更换为qbuser之后所有账户都无法登陆

问题成因：重新以qbuser启动后会改变配置文件，默认用户被重置为admin+密码adminadmin