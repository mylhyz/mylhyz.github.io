---
title: 环境快速切换
author: AyuLyt
date: 2024-07-26 11:01
updated: 2024-07-26 11:01
excerpt: 工作需要切换公司内网和外网的环境和一些版本，记录一下一些快捷操作
tags:
  - npm
  - jdk
---
# npm registry

配置 alias

```bash
# .bashrc / .zshrc
alias npm-default="npm config set registry https://registry.npmjs.org"
alias npm-taobao="npm config set registry https://registry.npmmirror.com"
```

.npmrc 文件

```
registry=https://registry.npmmirror.com
```

# JDK

alias

```bash
alias jdk8="export JAVA_HOME=/Library/Java/JavaVirtualMachines/temurin-8.jdk/Contents/Home"
alias jdk11="export JAVA_HOME=/Library/Java/JavaVirtualMachines/temurin-11.jdk/Contents/Home"
alias jdk17="export JAVA_HOME=/Library/Java/JavaVirtualMachines/amazon-corretto-17.jdk/Contents/Home"
alias jdk21="export JAVA_HOME=/Library/Java/JavaVirtualMachines/amazon-corretto-21.jdk/Contents/Home"
```

# git快捷

alias

```bash
function gcu() {
    # 获取当前时间
    now=$(date +'%Y-%m-%d %H:%M:%S')
    # 提交代码，并将当前时间追加到信息末尾
    git commit -m "UPDATE [$now]"
}

alias ga='git add --all'
alias gc='gcu'
alias gp='git push'
```

