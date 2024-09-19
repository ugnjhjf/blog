---
title: Centos 8 更换阿里源
published: 2024-09-17
description: ''
image: ''
tags: ['NAS','Docker','linux','后端','数据库','SMB','配置文件','omv']
category: '后端'
draft: false 
lang: ''
---


sed -i 's|mirrorlist=|#mirrorlist=|g' CentOS-Base.repo CentOS-AppStream.repo CentOS-Extras.repo
sed -i 's|#baseurl=|baseurl=|g' CentOS-Base.repo CentOS-AppStream.repo CentOS-Extras.repo
sed -i 's|<http://mirror.centos.org|https://mirrors.aliyun.com|g>' CentOS-Base.repo CentOS-AppStream.repo CentOS-Extras.repo
