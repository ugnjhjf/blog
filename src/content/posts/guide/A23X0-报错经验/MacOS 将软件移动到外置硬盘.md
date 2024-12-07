---
title: MacOS 将软件移动到外置硬盘
published: 2023-09-09
description: ""
tags: [MacOS, HDD]
category: Back-end
draft: false
---
教学：
https://zhuanlan.zhihu.com/p/670180068


# 让软件在外置硬盘也能被spotlight找到

打开终端，进入系统自带的软件目录

```shell
cd /Applications

mv /Volumes/RC20\ MacExtend/Applications/


ln -s /Volumes/External/Application/Android\ Studio.app ./Android\ Studio.app

ln -s /Volumes/RC20\ MacExtend/Applications/<App>.app <App>.app
```

因为软件名称中间有空格，所以之间会有个[斜杆](https://zhida.zhihu.com/search?q=%E6%96%9C%E6%9D%86&zhida_source=entity&is_preview=1)，你们的软件中间有的时候也需要注意。

这个时候，应用程序里就会有Android Studio.app 程序，Launchpad（启动台）也能有Android Studio图标，一样的点击打开。
