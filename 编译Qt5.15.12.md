---
title: 编译Qt5.15.12
author: AyuLyt
date: 2024-03-07 16:08
updated: 2024-03-07 16:08
excerpt: Mac和Windows下编译Qt5.15.12记录
tags:
  - qt
  - mac
  - windows
---
直接fork了官方仓库并在5.15.12版本上创建了分支
https://gitlab.com/qt5-project-x/qt5/-/tree/qt5-v5.15.12-build-macosx?ref_type=heads

# Mac

编译环境
```
# perl
This is perl 5, version 38, subversion 2 (v5.38.2) built for darwin-thread-multi-2level

# python
Python 2.7.18

# clang
Apple clang version 15.0.0 (clang-1500.3.9.4)
Target: x86_64-apple-darwin23.3.0
```

编译配置

```bash
./configure -prefix /Users/mylhyz/Downloads/qt5-libs -opensource -confirm-license -no-compile-examples -nomake examples -nomake tests
```


# Windows

编译环境

```
# perl
This is perl 5, version 32, subversion 1 (v5.32.1) built for MSWin32-x64-multi-thread

# python
Python 2.7.18

# clang
Apple clang version 15.0.0 (clang-1500.3.9.4)
Target: x86_64-apple-darwin23.3.0
```

编译配置
（如需使用msvc编译，在visual studio的命令行下运行configure即可）

```cmd
configure -prefix C:\github\qt5_install -opensource -confirm-license -nomake examples -nomake tests
```
