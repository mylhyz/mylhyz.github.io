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

编译配置

```bash
./configure -prefix /Users/mylhyz/Downloads/qt5-libs -opensource -confirm-license -no-compile-examples -nomake examples -nomake tests
```
