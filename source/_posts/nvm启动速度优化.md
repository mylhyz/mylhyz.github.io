---
title: nvm启动速度优化
author: AyuLyt
date: 2024-07-15 10:24
updated: 2024-07-15 10:24
excerpt: nvm启动阶段会进行一系列检查，对bash终端的启动速度有很大影响，这里介绍一种方法优化启动速度
tags:
  - nvm
  - bash
  - zsh
---

# 背景

首先可以根据这篇文章评估zsh启动耗时原因
- [https://spencer-blog-legacy.vercel.app/2020/07/remove-nvm-to-speed-up-zsh/](https://spencer-blog-legacy.vercel.app/2020/07/remove-nvm-to-speed-up-zsh/)

延迟优化方案网上有很多，大部分都是吐槽nvm不好用建议用其他工具的，如

- ⭐️fnm -  [https://github.com/Schniz/fnm](https://github.com/Schniz/fnm)
- volta - [https://volta.sh/](https://volta.sh/)


# 命令行参数 --no-use

通过分析nvm终端配置的启动参数

```bash
export NVM_DIR="$HOME/.nvm"

[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm

[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion" # This loads nvm bash_completion
```


在 nvm.sh 才是影响启动的核心，在脚本中找到一个参数 --no-use ，传入此参数就可以跳过nvm启动阶段默认切换node版本相关的检查


```bash
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" --no-use # This loads nvm
```