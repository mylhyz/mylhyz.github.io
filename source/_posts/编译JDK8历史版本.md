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

- 直接安装WindowsXP SP3的虚拟机并相关依赖工具

#### cygwin

使用支持winxp的版本
```bash
setup-x86.exe --allow-unsupported-windows --site http://ctm.crouchingtigerhiddenfruitbat.org/pub/cygwin/circa/2016/08/30/104223 --no-verify
```
必备工具命令
- git
- wget
- unzip
- zip
- cpio
- make
- gcc-g++

#### git

- 关闭crlf转换
- VisualStudio仅使用英文

# OpenJDK

- 所有tags https://hg.openjdk.java.net/jdk8u/monojdk8u/tags

根据需要找到版本号，如 jdk8u121-b36  https://hg.openjdk.java.net/jdk8u/monojdk8u/rev/8b0e3c5074f2


# 构建

配置
```bash
# bash configure --help 查看所有可用参数
./configure --with-boot-jdk=/cygdrive/c/App/Java/jdk1.7.0_80 --with-freetype=/cygdrive/c/App/freetype2 --with-jvm-variants=client --with-debug-level=fastdebug
```

编译
```bash
make CONF= all
```

# 报错处理

- Could not initialize class sun.font.SunFontManager

跟随jdk编译出的freetype2有问题，可以自己下载源码编译并在jdk编译时指定；
- 不能使用GnuWin32的freetype2

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

- the trustAnchors parameter must be non-empty

参考 https://www.baeldung.com/java-trustanchors-parameter-must-be-non-empty

默认编译出来的jdk是缺少一些证书，这里可以简单从已有的jdk中复制来解决
> 比如从 jdk1.8.0_121的 java/security 覆盖

