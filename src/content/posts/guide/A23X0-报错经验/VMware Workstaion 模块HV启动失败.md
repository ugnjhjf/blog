---
title: VMware Workstaion 模块HV启动失败
published: 2023-09-09
description: "abc"
tags: [VT-X, VMWare, Debug]
category: Back-end
draft: false
---
#虚拟机 #后端  #vmware #debug 
问题： 支持VT-X虚拟化技术的CPU无法在虚拟机中启用VT-X技术

解决方案：
1. 关闭所有与虚拟化相关的windows功能：包括虚拟机平台，虚拟机监控，HyperV，windows subsystem of linux
2. powershell 管理员执行以下命令
```powershell
   bcdedit /set hypervisorlaunchtype off
```

重启计算机