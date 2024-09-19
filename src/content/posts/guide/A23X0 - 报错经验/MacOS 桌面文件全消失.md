---
title: MacOS 桌面文件全消失
published: 2024-08-20
description: ''
image: ''
tags: ['MacOS','UI','终端','debug']
category: 'Mac'
draft: false 
lang: ''
---

# UI #macOS #报错经验 #终端

Mac文件全部在，但是桌面就是不显示。

原因：破解软件造成的桌面错误
解决方案：上面终端

```terminal
defaults write com.apple.finder CreateDesktop -bool true_; killall Finder_`
```
