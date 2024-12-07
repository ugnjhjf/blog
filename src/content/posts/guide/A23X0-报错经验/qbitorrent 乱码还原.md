---
title: qbitorrent 乱码还原
published: 2023-09-09
description: ""
tags: [Qbittorrent, server, network, linux]
category: Back-end
draft: false
---
若出现乱码，在地址栏后面加入 /api/v2/app/setPreferences?json=%7B%22alternative_webui_enabled%22:false%7D 进行返回原本 UI

乱码解决方式，查看自己路径是否正确