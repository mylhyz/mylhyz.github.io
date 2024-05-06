---
title: 编译JDK8历史版本
author: AyuLyt
date: 2024-05-06 10:39
updated: 2024-05-06 10:39
excerpt: 工作需要使用jdk8的历史版本jdk8u121，可以自己编译一个指定版本用于分析核心的内部实现
tags:
  - jdk
  - java
  - 旧版本支持
  - openjdk
---
# 参考资料

- https://openjdk.org/groups/build/doc/building.html

# 工具准备

- 参考 https://github.com/adoptium/temurin-build
- cygwin

# OpenJDK

- 所有tags https://hg.openjdk.java.net/jdk8u/monojdk8u/tags

根据需要找到版本号，如 jdk8u121-b36  https://hg.openjdk.java.net/jdk8u/monojdk8u/rev/8b0e3c5074f2


# 报错处理

- Could not initialize class sun.font.SunFontManager

跟随jdk编译出的freetype2有问题，可以自己下载源码编译并在jdk编译时指定

```
最终通过下载 
https://sourceforge.net/projects/freetype/files/freetype2/2.13.0/ 
并在WinXP上使用vs2010编译，将产物放到指定目录即可（jdk编译指定的freetype目录有格式要求）

-- include
---- freetype
---- ft2build.h
-- lib
---- freetype.dll
---- freetype.lib
```

