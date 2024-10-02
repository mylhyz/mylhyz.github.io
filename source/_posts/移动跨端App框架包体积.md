---
title: 移动App框架包体积
author: AyuLyt
date: 2024-09-30 21:41
updated: 2024-09-30 21:41
excerpt: 调查了一下主流的跨端开发App框架的包体积
tags:
  - android
  - ios
  - hybrid
---
# Expo React Native - Android

Expo和ReactNative都是基于相同的架构，开发一个简单的单页面应用包体积默认是：

- debug 149M
- release 58M

原因是默认包含了四个架构的包

- x86
- x86_64
- armeabi-v7a
- arm64-v8a

对比之下，release包中 js 代码的打包体积是 398kb


# Expo React Native - iOS

TODO


# Flutter - Android

Flutter默认打包apk支持按照abi切分，切分后的apk每个大约7M，如果不设置切分，默认的包体积是：

- release 18M

此时 release 包中 libapp.so 的大小是约 1.2M


# Flutter - iOS

TODO
