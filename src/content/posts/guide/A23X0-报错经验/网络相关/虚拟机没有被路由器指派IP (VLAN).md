---
title: 虚拟机没有被路由器指派IP
published: 2024-03-29
description: " "
image: ./cover.jpg
tags: [VLAN, network, IP, CentOS, linux]
category: Back-end
draft: false
---
#后端 #vlan #网络 #IP #报错经验
报错经验：2024年3月29日19:07:49

在此之前，下午排错了内存条，一条DDR3内存寄了。

<font color="#f79646">问题描述和过程：想把Centos 7 Nginx改成专用DDNS机，增加vSwitch和Port Group之后无法ping通和正常获取IP</font>

<font color="#9bbb59">解决方案：VLAN ID改一样</font>


**如果VLAN相同是不是才能ping同和进行数据交换？**

<font color="#ff0000">是的</font>，VLAN（Virtual Local Area Network，虚拟局域网络）的主要功能之一就是在逻辑上隔离网络，使得不同VLAN之间的设备在没有适当路由配置的情况下不能直接通信。如果两台设备位于相同的VLAN中，它们可以直接通信（假设没有其他安全策略阻止通信）。如果它们位于不同的VLAN中，那么除非有路由器或三层交换机来进行跨VLAN的路由设置，否则它们无法直接ping通或进行数据交换。

