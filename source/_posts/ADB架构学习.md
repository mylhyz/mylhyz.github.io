---
title: ADB架构学习
author: AyuLyt
date: 2024-05-16 11:45
updated: 2024-05-16 11:45
excerpt: ADB的使用是一种怎样的方式，一些工具如scrcpy是怎么生效的
tags:
  - android
  - adb
---
- https://pkiller.com/android/android-adb%E6%9E%B6%E6%9E%84%E5%8F%8A%E5%AE%9E%E7%8E%B0%E5%88%86%E6%9E%90/


PC端
- adb client 客户端命令
- adb server 服务器

手机端
- adbd 守护进程

端口号
- 5037 PC端
- 5038 手机端

模式
- USB 模式
- TCP/IP 模式

服务器
- 每隔1s，都从 /dev/bus/usb 扫描一次新增的USB设备
- socket事件循环，接受adb client的命令


adbd
- 系统启动之后会启动
- 监控来自adb的连接
- socket事件循环