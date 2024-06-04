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


参考
- https://www.cnblogs.com/bao0/articles/16769863.html
- https://blog.csdn.net/u012106306/article/details/107335892


# 修改hosts

- Android 11 LineageOS

分区文件系统无法简单挂载 /system


通过app修改