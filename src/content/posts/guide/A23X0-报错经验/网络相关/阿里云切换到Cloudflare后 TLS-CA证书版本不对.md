---
title: 阿里云切换到Cloudflare后 TLS-CA证书版本不对
published: 2024-09-10
description: 阿里云切换到Cloudflare后 TLS-CA证书版本不对
image: ./cover.jpg
tags: [CentOS, linux]
category: Back-end
draft: false
---
2024.09.10 Nginx网页除错经验
# 问题描述：

将服务器从阿里云挂到cloudflare之后报TLS版本错误
改回去之后Nginx炸了，本地可以访问，公网不行。

# 解决方案
将网页移动到Nginx服务器上，放弃双重反代，同时注意配置文件


原本

```nginx

server{ 
server_name yztech.work;
	location = / { 
		auth_basic off;
		alias /APPS/www/Cryst/SACE/; 
		index index.html; 
		try_files $uri $uri/index.html $uri.html=404; 
	}
```


第一个原因，没有配置通用处理

注意 <font color="#ff0000">=</font> ，<font color="#ff0000">=</font>代表只匹配这个
没有等于就通用处理

```nginx

server {
    server_name yztech.work;
    location = / {
        auth_basic off;
        alias /APPS/www/Cryst/SACE;
        index index.html;
        try_files $uri $uri/index.html $uri.html =404;
    }

    # 添加一个通用处理，处理资源加载问题
    location / {
        auth_basic off;
        root /APPS/www/Cryst/SACE;
        try_files $uri $uri/index.html $uri.html =404;
    }
}

```

第二个原因，权限不足

解决
```shell

sudo chmod -R 755 /APPS/www/Cryst/SACE

```
