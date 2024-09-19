---
title: Debian 11 mysql安装 没有GPG公钥
published: 2024-08-20
description: ''
image: ''
tags: ['debian','mysql','linux','数据库','网络','debug']
category: '后端'
draft: false 
lang: ''
---


# debian  #linux #mysql #报错经验 #SQL

```shell
root@Debian11:~# apt update
apt install mysql-server
命中:1 http://deb.debian.org/debian bullseye InRelease
命中:2 http://deb.debian.org/debian bullseye-updates InRelease
命中:3 http://security.debian.org/debian-security bullseye-security InRelease
获取:4 http://repo.mysql.com/apt/debian bullseye InRelease [17.9 kB]
错误:4 http://repo.mysql.com/apt/debian bullseye InRelease
  由于没有公钥，无法验证下列签名： NO_PUBKEY B7B3B788A8D3785C
正在读取软件包列表... 完成
W: GPG 错误：http://repo.mysql.com/apt/debian bullseye InRelease: 由于没有公钥，无法验证下列签名： NO_PUBKEY B7B3B788A8D3785C
E: 仓库 “http://repo.mysql.com/apt/debian bullseye InRelease” 没有数字签名。
N: 无法安全地用该源进行更新，所以默认禁用该源。
N: 参见 apt-secure(8) 手册以了解仓库创建和用户配置方面的细节。
正在读取软件包列表... 完成
正在分析软件包的依赖关系树... 完成
正在读取状态信息... 完成                 
没有可用的软件包 mysql-server，但是它被其它的软件包引用了。
这可能意味着这个缺失的软件包可能已被废弃，
或者只能在其他发布源中找到

E: 软件包 mysql-server 没有可安装候选


root@Debian11:~# apt-get update
命中:1 http://deb.debian.org/debian bullseye InRelease
命中:2 http://deb.debian.org/debian bullseye-updates InRelease 
获取:3 http://repo.mysql.com/apt/debian bullseye InRelease [17.9 kB]
命中:4 http://security.debian.org/debian-security bullseye-security InRelease
错误:3 http://repo.mysql.com/apt/debian bullseye InRelease
  由于没有公钥，无法验证下列签名： NO_PUBKEY B7B3B788A8D3785C
正在读取软件包列表... 完成
W: GPG 错误：http://repo.mysql.com/apt/debian bullseye InRelease: 由于没有公钥，无法验证下列签名： NO_PUBKEY B7B3B788A8D3785C
E: 仓库 “http://repo.mysql.com/apt/debian bullseye InRelease” 没有数字签名。
N: 无法安全地用该源进行更新，所以默认禁用该源。
N: 参见 apt-secure(8) 手册以了解仓库创建和用户配置方面的细节。
root@Debian11:~#


```

解决方案：

```shell

sudo apt-key adv --fetch-keys http://repo.mysql.com/RPM-GPG-KEY-mysql-2022
```
