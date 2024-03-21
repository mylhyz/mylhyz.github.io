---
title: Android-cpuinfo解读
author: AyuLyt
date: 2024-03-21 10:07
updated: 2024-03-21 10:07
excerpt: 通过adb获取设备的cpu信息
tags:
  - android
  - cpu
---
通过如下命令获取设备信息

```bash
adb shell cat /proc/cpuinfo
```

得到的输出类似

```Text
processor	: 1
BogoMIPS	: 48.00
Features	: half thumb fastmult vfp edsp neon vfpv3 tls vfpv4 idiva idivt evtstrm
CPU implementer	: 0x41
CPU architecture: 8
CPU variant	: 0x0
CPU part	: 0xd03
CPU revision	: 3

Hardware	: rockchip,rk3368
Revision	: 0000
Serial		: xxxxxxxxxxxxxxx
```

- processor
是CPU序号，多核情况下从0开始
- BogoMIPS
CPU频率
- Features
支持的特性，比如neon（加速指令集支持）
- CPU implementer
CPU架构（ARM等）
- CPU part
具体架构
- CPU revision
版本号

- Hardware
硬件信息


其中
- CPU implementer 和 part 值对应可参考 https://github.com/bp0/armids/blob/master/arm.ids
- 支持的特性可以通过 https://github.com/google/cpu_features 检查

