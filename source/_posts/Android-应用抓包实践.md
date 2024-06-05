---
title: Android抓包实践
author: AyuLyt
date: 2024-06-03 13:05
updated: 2024-06-03 13:05
excerpt: 工作需要在手机中对自己开发的app进行抓包，这里介绍几种方案
tags:
  - android
  - proxy
  - 抓包
  - https
---
# 同一局域网内抓包

简单来说就是将电脑作为代理服务器，手机通过设置代理服务器为电脑，能够是实现在PC上抓取手机流量，
常用的电脑侧软件就是Charles和fiddler

如果想要抓取https的请求需要手机预先安装好上述软件的根证书，来手动实现中间人拦截

但是唯一的限制就是电脑和手机的网络是在同一局域网内，在Wifi上体现就是路由器必须关闭AP隔离；

遗憾的是公司的网络是不互通的，此方案pass


参考
- https://www.cnblogs.com/bao0/articles/16769863.html
- https://blog.csdn.net/u012106306/article/details/107335892


# 手机端抓包软件

- https://github.com/reqable/reqable-app 原HttpCanary
- 如果无法安装证书，可以尝试在magisk中安装即可正常抓包

# tcpdump

https://www.androidtcpdump.com/

直接通过此方案可以一步到位抓取手机设备上几乎所有包，用来分析TCP/IP，HTTPS等的请求流程，失败原因都可以
参考：https://blog.csdn.net/csdnzouqi/article/details/111468462

# 修改hosts

- Android 11 LineageOS

分区文件系统无法简单挂载 /system，因此该方案pass

# Magisk插件修改hosts

https://github.com/gloeyisk/systemless-hosts

通过修改此模块的hosts文件并重打包；
可以解决上述方案中 hosts 无法修改的问题







