---
title: 安装Certbot和开启HTTPS
published: 2023-09-09
description: 通过Certbot和Let's Encrypt开启HTTPS加密

tags: [Certbot, Qbittorrent, CentOS, Linux]
category: Back-end
draft: false
---


#centos #https  #web #certbot #nginx  
1.yum install nginx 


2.修改配置文件（文件管理器打开直接复制vultr的配置）

【启动nginx】

3.打开防火墙(80和443)

【重启防火墙】

4.openwrt更改80的ip到服务器上

5.安装snapd

sudo dnf install epel-release
sudo dnf upgrade
sudo yum install snapd
sudo systemctl enable --now snapd.socket
sudo ln -s /var/lib/snapd/snap /snap
sudo snap install core
sudo snap refresh core

sudo snap install --classic certbot
sudo ln -s /snap/bin/certbot /usr/bin/certbot
sudo certbot --nginx