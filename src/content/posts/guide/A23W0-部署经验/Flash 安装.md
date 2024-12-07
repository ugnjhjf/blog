---
title: Flash安装
published: 2023-09-09
description: ""
tags: [CentOS, linux]
category: Back-end
draft: false
---

#flash #linux #centos #软件 #运维 

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