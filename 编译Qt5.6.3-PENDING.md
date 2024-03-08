---
title: 编译Qt5.6.3
author: AyuLyt
date: 2024-03-07 09:28
updated: 2024-03-07 09:28
excerpt: 想要开发一个支持WinXP的桌面端程序，Qt只有Qt5.6.3是最后一个支持WinXP的，尝试自己进行编译
tags:
  - qt
  - windows
  - mac
  - linux
---
> 由于在Mac上尝试编译直接就有相关报错，适配的问题较多，暂时搁置

实际上目前Qt5.6.3的安装包和源码还都是可以找到的
https://download.qt.io/new_archive/qt/5.6/5.6.3/


# Mac下编译

环境配置
```
```

编译配置
```

```

问题梳理
- 报错
```
zsh: ./configure: bad interpreter: /bin/sh^M: no such file or directory
```
原因是文件格式问题，在Unix下文件需要使用LF而不是CRLF，因此修改文件的终止符即可
- \_bit_scan_reverse 重复定义
clang新版本已经补充了了这个，从qt5.15.12中pick出 qtbase/src/corelib/global/qcompilerdetection.h 覆盖
- 报错
```
../include/QtCore/../../src/corelib/global/qcompilerdetection.h:609:6: error: Qt requires a C++11 compiler and yours does not seem to be that.
```
编译qmake

4404 CFG_STDCXX
