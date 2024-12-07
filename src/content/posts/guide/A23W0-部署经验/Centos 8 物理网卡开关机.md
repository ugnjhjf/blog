---
title: Centos 8 物理网卡开关机
published: 2023-09-09
description: Centos 8 物理网卡开关机
image: ./cover.jpg
tags: [CentOS, linux]
category: Back-end
draft: false
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