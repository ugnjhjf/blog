---
title: 戴尔服务器风扇开机自动调速
published: 2024-08-20
description: ''
image: ''
tags: ['服务器','后端','运维']
category: '后端'
draft: false 
lang: ''
---

# 服务器 #后端 #运维

## 戴尔服务器风扇开机自动调速

```sh
yum install ipmitool

ipmitool -I lanplus -U ipmi用户名 -P ipmi密码 -H 服务器地址 raw 0x30 0x30 0x01 0x00[[1]](#_ftn1)
```

0x00等于开启手动调速，0x01等于自动调速

```sh
ipmitool -I lanplus -U ipmi用户名 -P ipmi密码 -H 服务器地址 raw 0x30 0x30 0x02 0xff[[2]](#_ftn2) 0x18[[3]](#_ftn3)
```

0xff等于所有风扇；0x18为风扇运行的百分比，24的十六进制是18

可以利用ios 快捷指令的SSH自动执行

---

[[1]](#_ftnref1) 0x00等于开启手动调速

[[2]](#_ftnref2) 0xff等于所有风扇

[[3]](#_ftnref3) 0x18为风扇运行的百分比，24的十六进制是18
