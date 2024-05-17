---
title: JVM系统监控
author: AyuLyt
date: 2024-05-16 11:20
updated: 2024-05-16 11:20
excerpt: 使用JVM平台时如何对系统信息进行采样监控
tags:
  - jvm
  - sigar
  - oshi
---
- sigar 比较老，目前接近淘汰
	- 仅支持桌面平台

- oshi 比较新
	- 但是对Android的支持版本太高

```
- Windows 7 and higher. (Nearly all features work on Vista and most work on Windows XP.)
- macOS version 10.6 (Snow Leopard) and higher.
- Linux (Most major distributions) Kernel 2.6 and higher
- FreeBSD 10
- OpenBSD 6.8
- Solaris 11 (SunOS 5.11)
- AIX 7.1 (POWER4)
- Android 7.0 and higher
```