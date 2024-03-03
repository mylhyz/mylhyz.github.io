---
title: 折腾Termux配置
author: AyuLyt
date: 2024-03-03 13:06
updated: 2024-03-03 13:06
tags:
---
### 镜像

使用清华镜像
https://mirrors.tuna.tsinghua.edu.cn/help/termux/


# 软件包

- openssh
- vim
- git

- python
- nodejs-lts

# 配置

- sshd 需要手动开，或者写入到.bashrc中自动开启
- 可以使用adb forward 8022来映射设备的端口，这样在pc上就可以直接 ssh -p 8022 user@localhost 访问了
- git默认不会存储密码，需要手动配置 https://www.cnblogs.com/microestc/p/14309496.html
