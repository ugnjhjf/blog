---
title: Flash 安装
published: 2024-08-20
description: ''
image: ''
tags: ['服务器','后端','linux','软件']
category: '后端'
draft: false 
lang: ''
---


# flash #linux #centos #软件

**Flash x86_64****系统**  
  
```sh
wget http://linuxdownload.adobe.com/adobe-release/adobe-release-x86_64-1.0-1.noarch.rpm  
rpm -ivh adobe-release-x86_64-1.0-1.noarch.rpm  
rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY-adobe-linux  
yum install firefox.x86_64 flash-plugin  
  
```

更新 Flash player：  

```sh
yum update flash-plugin
```
