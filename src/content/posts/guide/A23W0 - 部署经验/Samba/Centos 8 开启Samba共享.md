---
title: Centos 8 开启Samba共享
published: 2024-08-26
description: ''
image: ''
tags: ['SMB','linux','centos']
category: '后端'
draft: false 
lang: ''
---

# centos #linux #samba #配置文件 #后端

安装Samba

```shell
yum install samba
```

启动Samba

```shell
systemctl restart smb 重启SMB
systemctl status smb 查看状态
```

配置Samba

```shell
vi /etc/samba/smb.conf
```

```shell
[share] 共享名

path = /NicoNico#实际路径

comment = lol 描述

valid users = UG #有效用户，空格分隔

write list = UG #允许读写的用户

#添加共享目录和用户，用户密码
```

# 新增用户

```shell
useradd UG

smbpasswd -a UG
```

查看目录权限

```shell
 ls -ld /NicoNico
```

授权文件夹所有者

```shell
chown UG /NicoNico
```

重启服务器

```shell
systemctl restart smb 重启SMB
systemctl status smb 查看状态
```

# 防火墙

设置防火墙规则

```shell
firewall-cmd --permanent --add-service=samba

firewall-cmd --permanent --add-service=samba-client

firewall-cmd --reload
```

关闭防火墙,selinux权限
将SELINUX=enforcing 改为 SELINUX=disabled

```shell

chcon -t samba_share_t /NicoNico #<-实际目录同上（授权！！！！）

ls -ldZ /NicoNico

systemctl stop firewalld #停止防火墙 
systemctl disable firewalld #永久停止防火墙

systemctl start firewalld 开启防火墙
```

samba配置例子

```shell
[Paimon]

comment = Paimon 1.12.2

path = /Paimon

valid users = UG

write list = UG

browsable = yes

read only = no

guest ok = yes

writable = yes


[Kyaruserver]

comment = KyaruCentOSServer

path = /KyaruServer

valid users = UG

write list = UG

browsable = yes

read only = no

guest ok = yes

writable = yes
```
