---
title: VMWare Workstation Pro ”此平台不支持虚拟化的AMD-RVI“ 的解决方案
published: 2023-09-09
description: "ABC"
tags: [VMWare, VT-X, AMD-RVI, hyper-V]
category: Back-end
draft: false
---
1. 关闭一下所有Windows功能
- Hyper-V
- Windows 沙盒
- Windows 虚拟机监控程序平台
- 容器
- 适用于Linux的Windows子系统
- 虚拟机平台

2. 关闭 Windows Defender功能
- 内存隔离

3. Bios 打开 VT-x / SVT

4. 尝试更新到最新的VMWare Workstation