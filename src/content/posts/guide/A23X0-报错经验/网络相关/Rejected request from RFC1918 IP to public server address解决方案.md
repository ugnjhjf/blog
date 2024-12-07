---
title: Rejected request from RFC1918 IP to public server address解决方案
published: 2023-09-09
description: iDRAC问题
image: ./cover.jpg
tags: [iDRAC, ESXI]
category: Back-end
draft: false
---
1.IDRAC安装ESXI
2.设置固定IP( ESXI)
3.设置网口独立 （vSwitch+VM Network）
4. !注意 ESXI不要启用所有口能够访问ESXI，这会造成扰乱以搞好的网口独立!!
5.配置OPENWRT
6.最后的最后才转小米WIFI桥接

开启DDNS后，通过公网IP或动态域名访问路由器时提示“Rejected request from RFC1918 IP to public server address”，将/etc/config/uhttpd 中的option rfc1918_filter 1改成option rfc1918_filter 0可解决这个问题。