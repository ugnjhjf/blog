---
title: Asu NAS部署经验
published: 2024-08-26
description: ''
image: ''
tags: ['NAS','Docker','linux','后端','数据库','SMB','配置文件','omv']
category: '后端'
draft: false 
lang: ''
---

OpenMediaVault

# 前情提要

重装了三次，绷不住了。

第一次装Docker，用了omv-developer之后连不上服务器了，也不知道为啥，难绷。

# 文件共享（开放SMB流程）

1. 格式化硬盘
   存储器 (Storage) -> 文件系统 -> + -> EXT4
2. 建立用户可用配置
   存储器 -> 共享文件夹 -> +
3. 新建用户
   用户->权限组包括: openmediavault-admin, root, sambashare, sudo, users
4. 开放SMB
    启用SMB
   SMB/CIFS -> 共享 -> 设置
   选择共享文件夹
   SMB/CIFS -> 共享 -> 共享

<font color="#ff0000">重要：点面板弹出的黄色勾确定应用，否则无效！！！</font>

# 网络错误：删除与Workstation直连光口后仍然找不到Host

进入ssh，root执行

```shell
systemctl restart networking.service
```

# PhotoPrism

## 网页插件版 无法启动

Podman和Docker有冲突，启用了omv-developer套件后提供的docker compose不能使用网页版的Photoprism，只能用Docker Container/Compose版本。

Compose 版本搞了一会实在不会搞，用了[[Docker container]]版本。

配置如下

```shell
docker run -d \

  --name photoprism \

  --security-opt seccomp=unconfined \

  --security-opt apparmor=unconfined \

  -p 2342:2342 \

  -e PHOTOPRISM_UPLOAD_NSFW="true" \

  -e PHOTOPRISM_ADMIN_PASSWORD="insecure" \
#不要动这一行
  -v /photoprism/storage \
#最后的/photoprism/originals不要改！否则会找不到文件
  -v /srv/dev-disk-by-uuid-/Main:/photoprism/originals \

  photoprism/photoprism

#<---------弹出一个Docker Container ID------------>
  
#改密码(用户名admin)
docker exec -ti photoprism photoprism passwd admin

docker start <Docker Container ID>

#记得开放端口，OMV网页防火墙可以做到这件事。  
```

# 其他

抽象MT-photo
头一个月免费使用，之后订阅
