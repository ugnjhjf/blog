---
title: Centos 8 上启动Minecraft服务器
published: 2024-08-20
description: ''
image: ''
tags: ['服务器','后端','linux','minecraft','centos']
category: '后端'
draft: false 
lang: ''
---



利用Samba进行传输服务器包，解压后进行下列操作

安装Java

```shell
yum install java
```

安装Screen

```shell
yum install screen
```

在Screen中继续操作

```shell
 screen -S MC
```

给脚本增加可执行权限

```shell
chmod +x ./start.sh
```

打开./start.sh编辑配置文件 或者 配置以下内容

```sh
    echo '+++++[FluctLight AI Console] Server will be running soon!+++++'
    java -Xms4096M -Xmx7128M -jar CatServer-1b57158-universal.jar
```

执行脚本

```sh
./start.sh
```

# 防火墙&端口

开放端口

```sh
firewall-cmd --add-port=25565/tcp --permanent   MC端口

firewall-cmd --add-port=10000/tcp --permanent 内网端口

```

返回Screen后台

```sh
screen -rx MC
```

映射(Sakura Frp - > frtp)

```sh
bash <(curl -s [https://getfrp.sh](https://getfrp.sh)
```
