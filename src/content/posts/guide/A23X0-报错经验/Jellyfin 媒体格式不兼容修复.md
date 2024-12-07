---
title: Jellyfin 媒体格式不兼容修复
published: 2023-09-09
description: ""
tags: [Jellyfin, server, network, ffmpeg, linux]
category: Back-end
draft: false
---
#Jellyfin #服务器 #运维 #网络 #ffmpeg 
sudo dnf -y install https://download.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm

sudo dnf localinstall --nogpgcheck https://download1.rpmfusion.org/free/el/rpmfusion-free-release-8.noarch.rpm

sudo dnf install --nogpgcheck https://download1.rpmfusion.org/nonfree/el/rpmfusion-nonfree-release-8.noarch.rpm

sudo dnf install http://rpmfind.net/linux/epel/7/x86_64/Packages/s/SDL2-2.0.10-1.el7.x86_64.rpm
http://rpmfind.net/linux/epel/7/x86_64/Packages/s/SDL2-2.0.14-2.el7.x86_64.rpm

注释：SDL2可能过期，前往http://rpmfind.net/linux/epel/7/x86_64/Packages/s/更改SDL2的数字


dnf update

sudo dnf install ffmpeg ffmpeg-devel

Jellyfin 编码,ffmpeg路径改为：
/usr/local/ffmpeg

找不到就whereis ffmpeg