---
title: Android-查看动态库编译使用的NDK版本
author: AyuLyt
date: 2024-04-19 15:45
updated: 2024-04-19 15:48
excerpt: 默认摘要
tags:
---

NDK官网可以查看每个NDK版本对应的clang版本
[https://developer.android.com/ndk/downloads/revision_history?hl=zh-cn](https://developer.android.com/ndk/downloads/revision_history?hl=zh-cn)

比如：android-ndk-r17
[https://github.com/android/ndk/wiki/Changelog-r17](https://github.com/android/ndk/wiki/Changelog-r17)

能够知道clang升级到了什么版本
- **Updated Clang to build 4691093, based on r316199**


在本地通过readelf查看so的信息就可以知道so编译使用的clang版本；

```bash
toolchains/arm-linux-androideabi-4.9/prebuilt/darwin-x86_64/bin/arm-linux-androideabi-readelf -p ".comment" libfb.so
```

```Text
String dump of section '.comment':
  [     1]  GCC: (GNU) 4.9.x 20150123 (prerelease)
  [    28]  Android (4691093 based on r316199) clang version 6.0.2 (https://android.googlesource.com/toolchain/clang 183abd29fc496f55536e7d904e0abae47888fc7f) (https://android.googlesource.com/toolchain/llvm 34361f192e41ed6e4e8f9aca80a4ea7e9856f327) (based on LLVM 6.0.2svn)
```
