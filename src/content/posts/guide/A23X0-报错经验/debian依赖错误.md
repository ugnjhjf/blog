---
title: Debian 11依赖错误
published: 2023-09-09
description: ""
image: ./cover.jpg
tags: [Debian, linux]
category: Back-end
draft: false
---
解决方法：到网页上手动安装


https://deb.debian.org/debian/pool/main/s/snakeyaml/




```shell
echidna@Debian11:~/apps/chatNexus$ sudo apt --fix-broken install
正在读取软件包列表... 完成
正在分析软件包的依赖关系树... 完成
正在读取状态信息... 完成                 
正在修复依赖关系... 完成
将会同时安装下列软件：
  default-jdk-doc libyaml-snake-java openjdk-11-doc
建议安装：
  default-jdk
下列【新】软件包将被安装：
  default-jdk-doc libyaml-snake-java openjdk-11-doc
升级了 0 个软件包，新安装了 3 个软件包，要卸载 0 个软件包，有 199 个软件包未被升级。
有 5 个软件包没有被完全安装或卸载。
需要下载 13.8 MB 的归档。
解压缩后会消耗 285 MB 的额外空间。
您希望继续执行吗？ [Y/n] y
获取:1 http://security.debian.org/debian-security bullseye-security/main amd64 openjdk-11-doc all 11.0.25+9-1~deb11u1 [13.5 MB]
错误:2 http://deb.debian.org/debian bullseye/main amd64 libyaml-snake-java all 1.28-1
  404  Not Found [IP: 151.101.2.132 80]
获取:3 http://deb.debian.org/debian bullseye/main amd64 default-jdk-doc amd64 2:1.11-72 [11.0 kB]
已下载 13.5 MB，耗时 1秒 (18.3 MB/s)                                               
E: 无法下载 http://deb.debian.org/debian/pool/main/s/snakeyaml/libyaml-snake-java_1.28-1_all.deb  404  Not Found [IP: 151.101.2.132 80]
E: 有几个软件包无法下载，要不运行 apt-get update 或者加上 --fix-missing 的选项再试试？
echidna@Debian11:~/apps/chatNexus$ sudo apt update --fix-missing
命中:1 http://repo.mysql.com/apt/debian bullseye InRelease
命中:2 http://deb.debian.org/debian bullseye InRelease                           
命中:3 http://deb.debian.org/debian bullseye-updates InRelease                   
命中:4 http://security.debian.org/debian-security bullseye-security InRelease
正在读取软件包列表... 完成
正在分析软件包的依赖关系树... 完成
正在读取状态信息... 完成                 
有 199 个软件包可以升级。请执行 ‘apt list --upgradable’ 来查看它们。
echidna@Debian11:~/apps/chatNexus$ sudo apt --fix-broken install
正在读取软件包列表... 完成
正在分析软件包的依赖关系树... 完成
正在读取状态信息... 完成                 
正在修复依赖关系... 完成
将会同时安装下列软件：
  default-jdk-doc libyaml-snake-java openjdk-11-doc
建议安装：
  default-jdk
下列【新】软件包将被安装：
  default-jdk-doc libyaml-snake-java openjdk-11-doc
升级了 0 个软件包，新安装了 3 个软件包，要卸载 0 个软件包，有 199 个软件包未被升级。
有 5 个软件包没有被完全安装或卸载。
需要下载 313 kB/13.8 MB 的归档。
解压缩后会消耗 285 MB 的额外空间。
您希望继续执行吗？ [Y/n] y
错误:1 http://deb.debian.org/debian bullseye/main amd64 libyaml-snake-java all 1.28-1
  404  Not Found [IP: 151.101.194.132 80]
E: 无法下载 http://deb.debian.org/debian/pool/main/s/snakeyaml/libyaml-snake-java_1.28-1_all.deb  404  Not Found [IP: 151.101.194.132 80]
E: 有几个软件包无法下载，要不运行 apt-get update 或者加上 --fix-missing 的选项再试试？
echidna@Debian11:~/apps/chatNexus$ wget https://deb.debian.org/debian/pool/main/s/snakeyaml/libyaml-snake-java_1.28-1+deb11u2_all.deb
--2024-11-18 20:03:56--  https://deb.debian.org/debian/pool/main/s/snakeyaml/libyaml-snake-java_1.28-1+deb11u2_all.deb
正在解析主机 deb.debian.org (deb.debian.org)... 151.101.2.132, 151.101.66.132, 151.101.130.132, ...
正在连接 deb.debian.org (deb.debian.org)|151.101.2.132|:443... 已连接。
已发出 HTTP 请求，正在等待回应... 200 OK
长度：313916 (307K) [application/vnd.debian.binary-package]
正在保存至: “libyaml-snake-java_1.28-1+deb11u2_all.deb”

libyaml-snake-java_1.28-1+deb11u2_all.deb     100%[=================================================================================================>] 306.56K   628KB/s  用时 0.5s    

2024-11-18 20:03:57 (628 KB/s) - 已保存 “libyaml-snake-java_1.28-1+deb11u2_all.deb” [313916/313916])

echidna@Debian11:~/apps/chatNexus$ sudo dpkg -i libyaml-snake-java_1.28-1+deb11u2_all.deb
正在选中未选择的软件包 libyaml-snake-java。
(正在读取数据库 ... 系统当前共安装有 157942 个文件和目录。)
准备解压 libyaml-snake-java_1.28-1+deb11u2_all.deb  ...
正在解压 libyaml-snake-java (1.28-1+deb11u2) ...
正在设置 libyaml-snake-java (1.28-1+deb11u2) ...
echidna@Debian11:~/apps/chatNexus$ sudo apt --fix-broken install
正在读取软件包列表... 完成
正在分析软件包的依赖关系树... 完成
正在读取状态信息... 完成                 
正在修复依赖关系... 完成
将会同时安装下列软件：
  default-jdk-doc openjdk-11-doc
建议安装：
  default-jdk
下列【新】软件包将被安装：
  default-jdk-doc openjdk-11-doc
升级了 0 个软件包，新安装了 2 个软件包，要卸载 0 个软件包，有 199 个软件包未被升级。
有 5 个软件包没有被完全安装或卸载。
需要下载 0 B/13.5 MB 的归档。
解压缩后会消耗 284 MB 的额外空间。
您希望继续执行吗？ [Y/n] y
正在选中未选择的软件包 openjdk-11-doc。
(正在读取数据库 ... 系统当前共安装有 158029 个文件和目录。)
准备解压 .../openjdk-11-doc_11.0.25+9-1~deb11u1_all.deb  ...
正在解压 openjdk-11-doc (11.0.25+9-1~deb11u1) ...
正在选中未选择的软件包 default-jdk-doc。
准备解压 .../default-jdk-doc_2%3a1.11-72_amd64.deb  ...
正在解压 default-jdk-doc (2:1.11-72) ...
正在设置 bnd (5.0.1-3) ...
正在设置 openjdk-11-doc (11.0.25+9-1~deb11u1) ...
正在设置 libgradle-plugins-java (4.4.1-13) ...
正在设置 libbindex-java (2.2+svn101-4) ...
正在设置 gradle (4.4.1-13) ...
正在设置 default-jdk-doc (2:1.11-72) ...
正在设置 libyaml-snake-java-doc (1.33-2) ...
echidna@Debian11:~/apps/chatNexus$ 
```

完成后apt-get update

```shell
sudo apt autoclean
sudo apt update
正在读取软件包列表... 完成
正在分析软件包的依赖关系树... 完成
正在读取状态信息... 完成                 
命中:1 http://repo.mysql.com/apt/debian bullseye InRelease
命中:2 http://deb.debian.org/debian bullseye InRelease                                                              
命中:3 http://deb.debian.org/debian bullseye-updates InRelease                                                      
获取:4 http://security.debian.org/debian-security bullseye-security InRelease [27.2 kB]
获取:5 http://security.debian.org/debian-security bullseye-security/main amd64 Packages [308 kB]
已下载 336 kB，耗时 1秒 (271 kB/s)
正在读取软件包列表... 完成
正在分析软件包的依赖关系树... 完成
正在读取状态信息... 完成                 
有 199 个软件包可以升级。请执行 ‘apt list --upgradable’ 来查看它们。
echidna@Debian11:~/apps/chatNexus$ sudo apt-get upgrade
正在读取软件包列表... 完成
正在分析软件包的依赖关系树... 完成
正在读取状态信息... 完成                 
正在计算更新... 完成
下列软件包是自动安装的并且现在不需要了：
  libdbus-glib-1-2 libopengl0 libwpe-1.0-1 libwpebackend-fdo-1.0-1
使用'sudo apt autoremove'来卸载它(它们)。
下列软件包的版本将保持不变：
  linux-image-amd64
下列软件包将被升级：
  apache2-bin bind9-dnsutils bind9-host bind9-libs bluez bluez-obexd bsdextrautils bsdutils cups cups-browsed cups-client cups-common cups-core-drivers cups-daemon cups-filters
  cups-filters-core-drivers cups-ipp-utils cups-ppdc cups-server-common distro-info-data e2fsprogs eject evolution evolution-common evolution-plugin-bogofilter
  evolution-plugin-pstimport evolution-plugins exfatprogs fdisk file firefox-esr firefox-esr-l10n-zh-tw fonts-opensymbol ghostscript gir1.2-gst-plugins-bad-1.0
  gir1.2-gst-plugins-base-1.0 gir1.2-javascriptcoregtk-4.0 gir1.2-lokdocview-0.1 gir1.2-rsvg-2.0 gir1.2-webkit2-4.0 gnome-shell gnome-shell-common gnome-shell-extension-prefs
  grub-common grub-pc grub-pc-bin grub2-common gstreamer1.0-gl gstreamer1.0-gtk3 gstreamer1.0-plugins-bad gstreamer1.0-plugins-base gstreamer1.0-plugins-good
  gstreamer1.0-plugins-ugly gstreamer1.0-pulseaudio gstreamer1.0-x krb5-locales less libaom0 libapr1 libarchive13 libavcodec58 libavfilter7 libavformat58 libavresample4 libavutil56
  libblkid1 libbluetooth3 libc-bin libc-l10n libc6 libcom-err2 libcue2 libcups2 libcupsfilters1 libcurl3-gnutls libcurl4 libdav1d4 libevolution libexpat1 libext2fs2 libfdisk1
  libflac8 libflatpak0 libfontembed1 libgit2-1.1 libglib2.0-0 libglib2.0-bin libglib2.0-data libgnutls30 libgs9 libgs9-common libgsf-1-114 libgsf-1-common libgsf-bin libgssapi-krb5-2
  libgstreamer-gl1.0-0 libgstreamer-plugins-bad1.0-0 libgstreamer-plugins-base1.0-0 libjavascriptcoregtk-4.0-18 libjson-c5 libjuh-java libjurt-java libk5crypto3 libkpathsea6
  libkrb5-3 libkrb5support0 liblibreoffice-java liblibreofficekitgtk libmagic-mgc libmagic1 libmount1 libndp0 libnghttp2-14 libnss-myhostname libnss-systemd libnss3 libpam-systemd
  libperl5.32 libpostproc55 libraw20 libreoffice-base-core libreoffice-calc libreoffice-common libreoffice-core libreoffice-draw libreoffice-gnome libreoffice-gtk3
  libreoffice-help-common libreoffice-help-en-us libreoffice-help-zh-tw libreoffice-impress libreoffice-l10n-zh-tw libreoffice-math libreoffice-style-colibre
  libreoffice-style-elementary libreoffice-writer libreofficekit-data libridl-java librsvg2-2 librsvg2-common libsepol1 libsmartcols1 libsmbclient libsqlite3-0 libss2 libssh-gcrypt-4
  libssl1.1 libswresample3 libswscale5 libsynctex2 libsystemd0 libtiff5 libudev1 libuno-cppu3 libuno-cppuhelpergcc3-3 libuno-purpenvhelpergcc3-3 libuno-sal3 libuno-salhelpergcc3-3
  libunoloader-java libuuid1 libuv1 libvpx6 libwbclient0 libwebkit2gtk-4.0-37 libwebp6 libwebpdemux2 libwebpmux3 libx11-data libxml2 libxpm4 libzbar0 locales logsave mount
  mysql-apt-config open-vm-tools open-vm-tools-desktop openssl perl perl-base perl-modules-5.32 python3-pkg-resources python3-uno samba-libs systemd systemd-sysv systemd-timesyncd
  tzdata udev uno-libs-private ure util-linux wpasupplicant xserver-common xserver-xephyr xserver-xorg-core xserver-xorg-legacy xwayland
升级了 198 个软件包，新安装了 0 个软件包，要卸载 0 个软件包，有 1 个软件包未被升级。
需要下载 333 MB 的归档。
解压缩后会消耗 51.2 MB 的额外空间。
您希望继续执行吗？ [Y/n] y
获取:1 http://security.debian.org/debian-security bullseye-security/main amd64 bsdutils amd64 1:2.36.1-8+deb11u2 [149 kB]
获取:2 http://deb.debian.org/debian bullseye-updates/main amd64 tzdata all 2021a-1+deb11u11 [287 kB]
获取:3 http://security.debian.org/debian-security bullseye-security/main amd64 libperl5.32 amd64 5.32.1-4+deb11u4 [4,132 kB]
获取:4 http://repo.mysql.com/apt/debian bullseye/mysql-apt-config amd64 mysql-apt-config all 0.8.29-1 [18.2 kB]
获取:5 http://security.debian.org/debian-security bullseye-security/main amd64 perl amd64 5.32.1-4+deb11u4 [293 kB]
获取:6 http://security.debian.org/debian-security bullseye-security/main amd64 perl-base amd64 5.32.1-4+deb11u4 [1,629 kB]
获取:7 http://security.debian.org/debian-security bullseye-security/main amd64 perl-modules-5.32 all 5.32.1-4+deb11u4 [2,824 kB]
获取:8 http://security.debian.org/debian-security bullseye-security/main amd64 libc6 amd64 2.31-13+deb11u10 [2,825 kB]
获取:9 http://security.debian.org/debian-security bullseye-security/main amd64 libblkid1 amd64 2.36.1-8+deb11u2 [194 kB]
获取:10 http://security.debian.org/debian-security bullseye-security/main amd64 libuuid1 amd64 2.36.1-8+deb11u2 [83.9 kB]
获取:11 http://security.debian.org/debian-security bullseye-security/main amd64 libfdisk1 amd64 2.36.1-8+deb11u2 [238 kB]
获取:12 http://security.debian.org/debian-security bullseye-security/main amd64 libmount1 amd64 2.36.1-8+deb11u2 [212 kB]
获取:13 http://security.debian.org/debian-security bullseye-security/main amd64 libsmartcols1 amd64 2.36.1-8+deb11u2 [158 kB]
获取:14 http://security.debian.org/debian-security bullseye-security/main amd64 fdisk amd64 2.36.1-8+deb11u2 [192 kB]
获取:15 http://security.debian.org/debian-security bullseye-security/main amd64 util-linux amd64 2.36.1-8+deb11u2 [1,142 kB]
获取:16 http://security.debian.org/debian-security bullseye-security/main amd64 libc-bin amd64 2.31-13+deb11u10 [827 kB]
获取:17 http://security.debian.org/debian-security bullseye-security/main amd64 xserver-common all 2:1.20.11-1+deb11u14 [2,285 kB]
获取:18 http://security.debian.org/debian-security bullseye-security/main amd64 xserver-xorg-legacy amd64 2:1.20.11-1+deb11u14 [2,290 kB]
获取:19 http://security.debian.org/debian-security bullseye-security/main amd64 libsystemd0 amd64 247.3-7+deb11u6 [377 kB]
获取:20 http://security.debian.org/debian-security bullseye-security/main amd64 xserver-xorg-core amd64 2:1.20.11-1+deb11u14 [3,604 kB]
获取:21 http://security.debian.org/debian-security bullseye-security/main amd64 systemd-timesyncd amd64 247.3-7+deb11u6 [131 kB]
获取:22 http://security.debian.org/debian-security bullseye-security/main amd64 libpam-systemd amd64 247.3-7+deb11u6 [283 kB]
获取:23 http://security.debian.org/debian-security bullseye-security/main amd64 libnss-systemd amd64 247.3-7+deb11u6 [199 kB]
获取:24 http://security.debian.org/debian-security bullseye-security/main amd64 systemd amd64 247.3-7+deb11u6 [4,501 kB]
获取:25 http://security.debian.org/debian-security bullseye-security/main amd64 bluez amd64 5.55-3.1+deb11u2 [1,140 kB]
获取:26 http://security.debian.org/debian-security bullseye-security/main amd64 udev amd64 247.3-7+deb11u6 [1,465 kB]
获取:27 http://security.debian.org/debian-security bullseye-security/main amd64 libudev1 amd64 247.3-7+deb11u6 [169 kB]
获取:28 http://security.debian.org/debian-security bullseye-security/main amd64 libglib2.0-data all 2.66.8-1+deb11u3 [1,177 kB]
获取:29 http://security.debian.org/debian-security bullseye-security/main amd64 libglib2.0-bin amd64 2.66.8-1+deb11u3 [142 kB]
获取:30 http://security.debian.org/debian-security bullseye-security/main amd64 libglib2.0-0 amd64 2.66.8-1+deb11u3 [1,376 kB]
获取:31 http://security.debian.org/debian-security bullseye-security/main amd64 systemd-sysv amd64 247.3-7+deb11u6 [114 kB]
获取:32 http://security.debian.org/debian-security bullseye-security/main amd64 libgnutls30 amd64 3.7.1-5+deb11u6 [1,340 kB]
获取:33 http://security.debian.org/debian-security bullseye-security/main amd64 mount amd64 2.36.1-8+deb11u2 [186 kB]
获取:34 http://security.debian.org/debian-security bullseye-security/main amd64 logsave amd64 1.46.2-2+deb11u1 [75.0 kB]
获取:35 http://security.debian.org/debian-security bullseye-security/main amd64 libext2fs2 amd64 1.46.2-2+deb11u1 [257 kB]
获取:36 http://security.debian.org/debian-security bullseye-security/main amd64 e2fsprogs amd64 1.46.2-2+deb11u1 [614 kB]
获取:37 http://security.debian.org/debian-security bullseye-security/main amd64 bsdextrautils amd64 2.36.1-8+deb11u2 [146 kB]
获取:38 http://security.debian.org/debian-security bullseye-security/main amd64 libk5crypto3 amd64 1.18.3-6+deb11u5 [114 kB]
获取:39 http://security.debian.org/debian-security bullseye-security/main amd64 libkrb5support0 amd64 1.18.3-6+deb11u5 [65.7 kB]
获取:40 http://security.debian.org/debian-security bullseye-security/main amd64 libkrb5-3 amd64 1.18.3-6+deb11u5 [363 kB]
获取:41 http://security.debian.org/debian-security bullseye-security/main amd64 libgssapi-krb5-2 amd64 1.18.3-6+deb11u5 [166 kB]
获取:42 http://security.debian.org/debian-security bullseye-security/main amd64 libcom-err2 amd64 1.46.2-2+deb11u1 [74.3 kB]
获取:43 http://security.debian.org/debian-security bullseye-security/main amd64 libssl1.1 amd64 1.1.1w-0+deb11u2 [1,565 kB]
获取:44 http://security.debian.org/debian-security bullseye-security/main amd64 cups-daemon amd64 2.3.3op2-3+deb11u9 [429 kB]
获取:45 http://security.debian.org/debian-security bullseye-security/main amd64 cups-ipp-utils amd64 2.3.3op2-3+deb11u9 [292 kB]
获取:46 http://security.debian.org/debian-security bullseye-security/main amd64 cups-common all 2.3.3op2-3+deb11u9 [314 kB]
获取:47 http://security.debian.org/debian-security bullseye-security/main amd64 cups-client amd64 2.3.3op2-3+deb11u9 [242 kB]
获取:48 http://security.debian.org/debian-security bullseye-security/main amd64 libwebp6 amd64 0.6.1-2.1+deb11u2 [259 kB]
获取:49 http://security.debian.org/debian-security bullseye-security/main amd64 libtiff5 amd64 4.2.0-1+deb11u5 [290 kB]
获取:50 http://security.debian.org/debian-security bullseye-security/main amd64 libcupsfilters1 amd64 1.28.7-1+deb11u3 [145 kB]
获取:51 http://security.debian.org/debian-security bullseye-security/main amd64 cups-filters-core-drivers amd64 1.28.7-1+deb11u3 [218 kB]
获取:52 http://security.debian.org/debian-security bullseye-security/main amd64 cups-core-drivers amd64 2.3.3op2-3+deb11u9 [146 kB]
获取:53 http://security.debian.org/debian-security bullseye-security/main amd64 libfontembed1 amd64 1.28.7-1+deb11u3 [75.4 kB]
获取:54 http://security.debian.org/debian-security bullseye-security/main amd64 ghostscript amd64 9.53.3~dfsg-7+deb11u8 [98.6 kB]
获取:55 http://security.debian.org/debian-security bullseye-security/main amd64 libgs9 amd64 9.53.3~dfsg-7+deb11u8 [2,243 kB]
获取:56 http://security.debian.org/debian-security bullseye-security/main amd64 libgs9-common all 9.53.3~dfsg-7+deb11u8 [735 kB]
获取:57 http://security.debian.org/debian-security bullseye-security/main amd64 cups-browsed amd64 1.28.7-1+deb11u3 [161 kB]
获取:58 http://security.debian.org/debian-security bullseye-security/main amd64 cups-filters amd64 1.28.7-1+deb11u3 [584 kB]
获取:59 http://security.debian.org/debian-security bullseye-security/main amd64 cups-ppdc amd64 2.3.3op2-3+deb11u9 [209 kB]
获取:60 http://security.debian.org/debian-security bullseye-security/main amd64 cups-server-common all 2.3.3op2-3+deb11u9 [520 kB]
获取:61 http://security.debian.org/debian-security bullseye-security/main amd64 cups amd64 2.3.3op2-3+deb11u9 [379 kB]
获取:62 http://security.debian.org/debian-security bullseye-security/main amd64 libcups2 amd64 2.3.3op2-3+deb11u9 [351 kB]
获取:63 http://security.debian.org/debian-security bullseye-security/main amd64 libsmbclient amd64 2:4.13.13+dfsg-1~deb11u6 [170 kB]
获取:64 http://security.debian.org/debian-security bullseye-security/main amd64 samba-libs amd64 2:4.13.13+dfsg-1~deb11u6 [5,778 kB]
获取:65 http://security.debian.org/debian-security bullseye-security/main amd64 libwbclient0 amd64 2:4.13.13+dfsg-1~deb11u6 [314 kB]
获取:66 http://security.debian.org/debian-security bullseye-security/main amd64 libsepol1 amd64 3.1-1+deb11u1 [269 kB]
获取:67 http://security.debian.org/debian-security bullseye-security/main amd64 less amd64 551-2+deb11u2 [136 kB]
获取:68 http://security.debian.org/debian-security bullseye-security/main amd64 libuv1 amd64 1.40.0-2+deb11u1 [132 kB]
获取:69 http://security.debian.org/debian-security bullseye-security/main amd64 libjson-c5 amd64 0.15-2+deb11u1 [42.9 kB]
获取:70 http://security.debian.org/debian-security bullseye-security/main amd64 libxml2 amd64 2.9.10+dfsg-6.7+deb11u5 [693 kB]
获取:71 http://security.debian.org/debian-security bullseye-security/main amd64 bind9-dnsutils amd64 1:9.16.50-1~deb11u1 [408 kB]
获取:72 http://security.debian.org/debian-security bullseye-security/main amd64 bind9-libs amd64 1:9.16.50-1~deb11u1 [1,430 kB]
获取:73 http://security.debian.org/debian-security bullseye-security/main amd64 bind9-host amd64 1:9.16.50-1~deb11u1 [312 kB]
获取:74 http://security.debian.org/debian-security bullseye-security/main amd64 file amd64 1:5.39-3+deb11u1 [69.2 kB]
获取:75 http://security.debian.org/debian-security bullseye-security/main amd64 libmagic1 amd64 1:5.39-3+deb11u1 [128 kB]
获取:76 http://security.debian.org/debian-security bullseye-security/main amd64 libmagic-mgc amd64 1:5.39-3+deb11u1 [273 kB]
获取:77 http://security.debian.org/debian-security bullseye-security/main amd64 krb5-locales all 1.18.3-6+deb11u5 [95.7 kB]
获取:78 http://security.debian.org/debian-security bullseye-security/main amd64 libc-l10n all 2.31-13+deb11u10 [864 kB]
获取:79 http://security.debian.org/debian-security bullseye-security/main amd64 locales all 2.31-13+deb11u10 [4,083 kB]
获取:80 http://security.debian.org/debian-security bullseye-security/main amd64 libapr1 amd64 1.7.0-6+deb11u2 [106 kB]
获取:81 http://security.debian.org/debian-security bullseye-security/main amd64 libnghttp2-14 amd64 1.43.0-1+deb11u2 [77.0 kB]
获取:82 http://security.debian.org/debian-security bullseye-security/main amd64 libcurl4 amd64 7.74.0-1.3+deb11u14 [348 kB]
获取:83 http://security.debian.org/debian-security bullseye-security/main amd64 apache2-bin amd64 2.4.62-1~deb11u2 [1,453 kB]
获取:84 http://security.debian.org/debian-security bullseye-security/main amd64 bluez-obexd amd64 5.55-3.1+deb11u2 [223 kB]
获取:85 http://security.debian.org/debian-security bullseye-security/main amd64 distro-info-data all 0.51+deb11u7 [8,436 B]
获取:86 http://security.debian.org/debian-security bullseye-security/main amd64 eject amd64 2.36.1-8+deb11u2 [103 kB]
获取:87 http://security.debian.org/debian-security bullseye-security/main amd64 libgstreamer-plugins-base1.0-0 amd64 1.18.4-2+deb11u2 [2,156 kB]
获取:88 http://security.debian.org/debian-security bullseye-security/main amd64 libgstreamer-gl1.0-0 amd64 1.18.4-2+deb11u2 [1,520 kB]
获取:89 http://security.debian.org/debian-security bullseye-security/main amd64 gstreamer1.0-gl amd64 1.18.4-2+deb11u2 [1,458 kB]
获取:90 http://security.debian.org/debian-security bullseye-security/main amd64 libflac8 amd64 1.3.3-2+deb11u2 [112 kB]
获取:91 http://security.debian.org/debian-security bullseye-security/main amd64 libvpx6 amd64 1.9.0-1+deb11u3 [829 kB]
获取:92 http://security.debian.org/debian-security bullseye-security/main amd64 gstreamer1.0-plugins-ugly amd64 1.18.4-2+deb11u1 [394 kB]
获取:93 http://security.debian.org/debian-security bullseye-security/main amd64 gstreamer1.0-gtk3 amd64 1.18.4-2+deb11u2 [1,377 kB]
获取:94 http://security.debian.org/debian-security bullseye-security/main amd64 gstreamer1.0-plugins-base amd64 1.18.4-2+deb11u2 [1,984 kB]
获取:95 http://security.debian.org/debian-security bullseye-security/main amd64 gstreamer1.0-plugins-bad amd64 1.18.4-3+deb11u4 [4,172 kB]
获取:96 http://security.debian.org/debian-security bullseye-security/main amd64 gstreamer1.0-plugins-good amd64 1.18.4-2+deb11u2 [3,169 kB]
获取:97 http://security.debian.org/debian-security bullseye-security/main amd64 libaom0 amd64 1.0.0.errata1-3+deb11u2 [1,121 kB]
获取:98 http://security.debian.org/debian-security bullseye-security/main amd64 libcurl3-gnutls amd64 7.74.0-1.3+deb11u14 [344 kB]
获取:99 http://security.debian.org/debian-security bullseye-security/main amd64 libgstreamer-plugins-bad1.0-0 amd64 1.18.4-3+deb11u4 [2,292 kB]
获取:100 http://security.debian.org/debian-security bullseye-security/main amd64 librsvg2-common amd64 2.50.3+dfsg-1+deb11u1 [31.2 kB]
获取:101 http://security.debian.org/debian-security bullseye-security/main amd64 librsvg2-2 amd64 2.50.3+dfsg-1+deb11u1 [2,462 kB]
获取:102 http://security.debian.org/debian-security bullseye-security/main amd64 libzbar0 amd64 0.23.90-1+deb11u1 [133 kB]
获取:103 http://security.debian.org/debian-security bullseye-security/main amd64 libsqlite3-0 amd64 3.34.1-3+deb11u1 [797 kB]
获取:104 http://security.debian.org/debian-security bullseye-security/main amd64 libwebpdemux2 amd64 0.6.1-2.1+deb11u2 [87.8 kB]
获取:105 http://security.debian.org/debian-security bullseye-security/main amd64 gir1.2-webkit2-4.0 amd64 2.44.3-1~deb11u1 [127 kB]
获取:106 http://security.debian.org/debian-security bullseye-security/main amd64 libwebkit2gtk-4.0-37 amd64 2.44.3-1~deb11u1 [19.1 MB]
获取:107 http://security.debian.org/debian-security bullseye-security/main amd64 gir1.2-javascriptcoregtk-4.0 amd64 2.44.3-1~deb11u1 [74.1 kB]
获取:108 http://security.debian.org/debian-security bullseye-security/main amd64 libjavascriptcoregtk-4.0-18 amd64 2.44.3-1~deb11u1 [6,624 kB]
获取:109 http://security.debian.org/debian-security bullseye-security/main amd64 libnss3 amd64 2:3.61-1+deb11u4 [1,304 kB]
获取:110 http://security.debian.org/debian-security bullseye-security/main amd64 evolution-plugin-pstimport amd64 3.38.3-1+deb11u2 [55.7 kB]
获取:111 http://security.debian.org/debian-security bullseye-security/main amd64 evolution-plugin-bogofilter amd64 3.38.3-1+deb11u2 [44.1 kB]
获取:112 http://security.debian.org/debian-security bullseye-security/main amd64 libevolution amd64 3.38.3-1+deb11u2 [2,505 kB]
获取:113 http://security.debian.org/debian-security bullseye-security/main amd64 evolution-plugins amd64 3.38.3-1+deb11u2 [108 kB]
获取:114 http://security.debian.org/debian-security bullseye-security/main amd64 evolution amd64 3.38.3-1+deb11u2 [322 kB]
获取:115 http://security.debian.org/debian-security bullseye-security/main amd64 evolution-common all 3.38.3-1+deb11u2 [7,348 kB]
获取:116 http://security.debian.org/debian-security bullseye-security/main amd64 exfatprogs amd64 1.1.0-1+deb11u1 [37.3 kB]
获取:117 http://security.debian.org/debian-security bullseye-security/main amd64 firefox-esr-l10n-zh-tw all 128.4.0esr-1~deb11u1 [686 kB]
获取:118 http://security.debian.org/debian-security bullseye-security/main amd64 firefox-esr amd64 128.4.0esr-1~deb11u1 [70.1 MB]
获取:119 http://security.debian.org/debian-security bullseye-security/main amd64 fonts-opensymbol all 2:102.11+LibO7.0.4-4+deb11u11 [286 kB]
获取:120 http://security.debian.org/debian-security bullseye-security/main amd64 gir1.2-gst-plugins-base-1.0 amd64 1.18.4-2+deb11u2 [1,436 kB]
获取:121 http://security.debian.org/debian-security bullseye-security/main amd64 gir1.2-gst-plugins-bad-1.0 amd64 1.18.4-3+deb11u4 [1,940 kB]
获取:122 http://security.debian.org/debian-security bullseye-security/main amd64 libreofficekit-data all 1:7.0.4-4+deb11u11 [203 kB]
获取:123 http://security.debian.org/debian-security bullseye-security/main amd64 gir1.2-lokdocview-0.1 amd64 1:7.0.4-4+deb11u11 [203 kB]
获取:124 http://security.debian.org/debian-security bullseye-security/main amd64 liblibreofficekitgtk amd64 1:7.0.4-4+deb11u11 [268 kB]
获取:125 http://security.debian.org/debian-security bullseye-security/main amd64 gir1.2-rsvg-2.0 amd64 2.50.3+dfsg-1+deb11u1 [30.2 kB]
获取:126 http://security.debian.org/debian-security bullseye-security/main amd64 gnome-shell-extension-prefs amd64 3.38.6-1~deb11u2 [43.7 kB]
获取:127 http://security.debian.org/debian-security bullseye-security/main amd64 gnome-shell amd64 3.38.6-1~deb11u2 [829 kB]
获取:128 http://security.debian.org/debian-security bullseye-security/main amd64 gnome-shell-common all 3.38.6-1~deb11u2 [745 kB]
获取:129 http://security.debian.org/debian-security bullseye-security/main amd64 grub2-common amd64 2.06-3~deb11u6 [611 kB]
获取:130 http://security.debian.org/debian-security bullseye-security/main amd64 grub-pc amd64 2.06-3~deb11u6 [131 kB]
获取:131 http://security.debian.org/debian-security bullseye-security/main amd64 grub-pc-bin amd64 2.06-3~deb11u6 [993 kB]
获取:132 http://security.debian.org/debian-security bullseye-security/main amd64 grub-common amd64 2.06-3~deb11u6 [2,767 kB]
获取:133 http://security.debian.org/debian-security bullseye-security/main amd64 gstreamer1.0-pulseaudio amd64 1.18.4-2+deb11u2 [1,361 kB]
获取:134 http://security.debian.org/debian-security bullseye-security/main amd64 gstreamer1.0-x amd64 1.18.4-2+deb11u2 [1,423 kB]
获取:135 http://security.debian.org/debian-security bullseye-security/main amd64 libarchive13 amd64 3.4.3-2+deb11u2 [343 kB]
获取:136 http://security.debian.org/debian-security bullseye-security/main amd64 libavfilter7 amd64 7:4.3.8-0+deb11u1 [1,304 kB]
获取:137 http://security.debian.org/debian-security bullseye-security/main amd64 libswscale5 amd64 7:4.3.8-0+deb11u1 [216 kB]
获取:138 http://security.debian.org/debian-security bullseye-security/main amd64 libavformat58 amd64 7:4.3.8-0+deb11u1 [1,062 kB]
获取:139 http://security.debian.org/debian-security bullseye-security/main amd64 libavcodec58 amd64 7:4.3.8-0+deb11u1 [4,970 kB]
获取:140 http://security.debian.org/debian-security bullseye-security/main amd64 libswresample3 amd64 7:4.3.8-0+deb11u1 [114 kB]
获取:141 http://security.debian.org/debian-security bullseye-security/main amd64 libpostproc55 amd64 7:4.3.8-0+deb11u1 [112 kB]
获取:142 http://security.debian.org/debian-security bullseye-security/main amd64 libavresample4 amd64 7:4.3.8-0+deb11u1 [111 kB]
获取:143 http://security.debian.org/debian-security bullseye-security/main amd64 libavutil56 amd64 7:4.3.8-0+deb11u1 [317 kB]
获取:144 http://security.debian.org/debian-security bullseye-security/main amd64 libssh-gcrypt-4 amd64 0.9.8-0+deb11u1 [221 kB]
获取:145 http://security.debian.org/debian-security bullseye-security/main amd64 libdav1d4 amd64 0.7.1-3+deb11u1 [331 kB]
获取:146 http://security.debian.org/debian-security bullseye-security/main amd64 libwebpmux3 amd64 0.6.1-2.1+deb11u2 [97.7 kB]
获取:147 http://security.debian.org/debian-security bullseye-security/main amd64 libbluetooth3 amd64 5.55-3.1+deb11u2 [112 kB]
获取:148 http://security.debian.org/debian-security bullseye-security/main amd64 libcue2 amd64 2.2.1-3+deb11u1 [22.7 kB]
获取:149 http://security.debian.org/debian-security bullseye-security/main amd64 libexpat1 amd64 2.2.10-2+deb11u6 [99.0 kB]
获取:150 http://security.debian.org/debian-security bullseye-security/main amd64 libflatpak0 amd64 1.10.8-0+deb11u2 [352 kB]
获取:151 http://security.debian.org/debian-security bullseye-security/main amd64 libgit2-1.1 amd64 1.1.0+dfsg.1-4+deb11u2 [445 kB]
获取:152 http://security.debian.org/debian-security bullseye-security/main amd64 libgsf-1-common all 1.14.47-1+deb11u1 [156 kB]
获取:153 http://security.debian.org/debian-security bullseye-security/main amd64 libgsf-1-114 amd64 1.14.47-1+deb11u1 [161 kB]
获取:154 http://security.debian.org/debian-security bullseye-security/main amd64 libgsf-bin amd64 1.14.47-1+deb11u1 [78.0 kB]
获取:155 http://security.debian.org/debian-security bullseye-security/main amd64 libridl-java all 1:7.0.4-4+deb11u11 [202 kB]
获取:156 http://security.debian.org/debian-security bullseye-security/main amd64 libjuh-java all 1:7.0.4-4+deb11u11 [202 kB]
获取:157 http://security.debian.org/debian-security bullseye-security/main amd64 libjurt-java all 1:7.0.4-4+deb11u11 [202 kB]
获取:158 http://security.debian.org/debian-security bullseye-security/main amd64 ure amd64 1:7.0.4-4+deb11u11 [1,338 kB]
获取:159 http://security.debian.org/debian-security bullseye-security/main amd64 libunoloader-java all 1:7.0.4-4+deb11u11 [206 kB]
获取:160 http://security.debian.org/debian-security bullseye-security/main amd64 liblibreoffice-java all 1:7.0.4-4+deb11u11 [1,812 kB]
获取:161 http://security.debian.org/debian-security bullseye-security/main amd64 libuno-sal3 amd64 1:7.0.4-4+deb11u11 [363 kB]
获取:162 http://security.debian.org/debian-security bullseye-security/main amd64 libuno-salhelpergcc3-3 amd64 1:7.0.4-4+deb11u11 [211 kB]
获取:163 http://security.debian.org/debian-security bullseye-security/main amd64 libuno-cppu3 amd64 1:7.0.4-4+deb11u11 [277 kB]
获取:164 http://security.debian.org/debian-security bullseye-security/main amd64 libuno-cppuhelpergcc3-3 amd64 1:7.0.4-4+deb11u11 [490 kB]
获取:165 http://security.debian.org/debian-security bullseye-security/main amd64 uno-libs-private amd64 1:7.0.4-4+deb11u11 [411 kB]
获取:166 http://security.debian.org/debian-security bullseye-security/main amd64 libuno-purpenvhelpergcc3-3 amd64 1:7.0.4-4+deb11u11 [210 kB]
获取:167 http://security.debian.org/debian-security bullseye-security/main amd64 libkpathsea6 amd64 2020.20200327.54578-7+deb11u2 [173 kB]
获取:168 http://security.debian.org/debian-security bullseye-security/main amd64 libndp0 amd64 1.6-1+deb11u1 [10.8 kB]
获取:169 http://security.debian.org/debian-security bullseye-security/main amd64 libnss-myhostname amd64 247.3-7+deb11u6 [141 kB]
获取:170 http://security.debian.org/debian-security bullseye-security/main amd64 libraw20 amd64 0.20.2-1+deb11u1 [350 kB]
获取:171 http://security.debian.org/debian-security bullseye-security/main amd64 libreoffice-calc amd64 1:7.0.4-4+deb11u11 [7,680 kB]
获取:172 http://security.debian.org/debian-security bullseye-security/main amd64 libreoffice-impress amd64 1:7.0.4-4+deb11u11 [1,299 kB]
获取:173 http://security.debian.org/debian-security bullseye-security/main amd64 libreoffice-draw amd64 1:7.0.4-4+deb11u11 [2,926 kB]
获取:174 http://security.debian.org/debian-security bullseye-security/main amd64 libreoffice-gnome amd64 1:7.0.4-4+deb11u11 [251 kB]
获取:175 http://security.debian.org/debian-security bullseye-security/main amd64 libreoffice-gtk3 amd64 1:7.0.4-4+deb11u11 [624 kB]
获取:176 http://security.debian.org/debian-security bullseye-security/main amd64 python3-uno amd64 1:7.0.4-4+deb11u11 [326 kB]
获取:177 http://security.debian.org/debian-security bullseye-security/main amd64 libreoffice-math amd64 1:7.0.4-4+deb11u11 [608 kB]
获取:178 http://security.debian.org/debian-security bullseye-security/main amd64 libreoffice-base-core amd64 1:7.0.4-4+deb11u11 [1,049 kB]
获取:179 http://security.debian.org/debian-security bullseye-security/main amd64 libreoffice-writer amd64 1:7.0.4-4+deb11u11 [9,144 kB]
获取:180 http://security.debian.org/debian-security bullseye-security/main amd64 libreoffice-core amd64 1:7.0.4-4+deb11u11 [34.3 MB]
获取:181 http://security.debian.org/debian-security bullseye-security/main amd64 libreoffice-help-zh-tw all 1:7.0.4-4+deb11u11 [3,324 kB]
获取:182 http://security.debian.org/debian-security bullseye-security/main amd64 libreoffice-help-en-us all 1:7.0.4-4+deb11u11 [1,588 kB]
获取:183 http://security.debian.org/debian-security bullseye-security/main amd64 libreoffice-help-common all 1:7.0.4-4+deb11u11 [3,349 kB]
获取:184 http://security.debian.org/debian-security bullseye-security/main amd64 libreoffice-common all 1:7.0.4-4+deb11u11 [18.7 MB]
获取:185 http://security.debian.org/debian-security bullseye-security/main amd64 libreoffice-l10n-zh-tw all 1:7.0.4-4+deb11u11 [824 kB]
获取:186 http://security.debian.org/debian-security bullseye-security/main amd64 libreoffice-style-colibre all 1:7.0.4-4+deb11u11 [1,419 kB]
获取:187 http://security.debian.org/debian-security bullseye-security/main amd64 libreoffice-style-elementary all 1:7.0.4-4+deb11u11 [7,656 kB]
获取:188 http://security.debian.org/debian-security bullseye-security/main amd64 libss2 amd64 1.46.2-2+deb11u1 [78.9 kB]
获取:189 http://security.debian.org/debian-security bullseye-security/main amd64 libsynctex2 amd64 2020.20200327.54578-7+deb11u2 [83.7 kB]
获取:190 http://security.debian.org/debian-security bullseye-security/main amd64 libx11-data all 2:1.7.2-1+deb11u2 [311 kB]
获取:191 http://security.debian.org/debian-security bullseye-security/main amd64 libxpm4 amd64 1:3.5.12-1.1+deb11u1 [50.0 kB]
获取:192 http://security.debian.org/debian-security bullseye-security/main amd64 open-vm-tools amd64 2:11.2.5-2+deb11u3 [632 kB]
获取:193 http://security.debian.org/debian-security bullseye-security/main amd64 open-vm-tools-desktop amd64 2:11.2.5-2+deb11u3 [166 kB]
获取:194 http://security.debian.org/debian-security bullseye-security/main amd64 openssl amd64 1.1.1w-0+deb11u2 [859 kB]
获取:195 http://security.debian.org/debian-security bullseye-security/main amd64 python3-pkg-resources all 52.0.0-4+deb11u1 [190 kB]
获取:196 http://security.debian.org/debian-security bullseye-security/main amd64 wpasupplicant amd64 2:2.9.0-21+deb11u2 [1,285 kB]
获取:197 http://security.debian.org/debian-security bullseye-security/main amd64 xserver-xephyr amd64 2:1.20.11-1+deb11u14 [3,181 kB]
获取:198 http://security.debian.org/debian-security bullseye-security/main amd64 xwayland amd64 2:1.20.11-1+deb11u14 [3,133 kB]
已下载 333 MB，耗时 6秒 (56.1 MB/s)   
读取变更记录(changelogs)... 59%
```