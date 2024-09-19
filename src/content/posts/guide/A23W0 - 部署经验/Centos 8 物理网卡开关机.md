---
title: Centos 8 物理关机/开机卡关机
published: 2024-08-20
description: ''
image: ''
tags: ['服务器','后端','linux','centos']
category: '后端'
draft: false 
lang: ''
---


## 物理关机/开机卡关机

安装acpid服务（电源高级接口配置）

```shell
       yum install acpid -y
```

启用

```shell

     systemctl enable acpid

     systemctl restart acpid

     reboot
```
