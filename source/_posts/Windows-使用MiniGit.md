---
title: Windows使用MiniGit
author: AyuLyt
date: 2024-03-03 13:07
updated: 2024-03-03 13:07
excerpt: 解决Windows下Git打开慢的问题
tags:
  - windows
  - git
---
- 需要额外安装 https://github.com/git-ecosystem/git-credential-manager
安装后还需要执行一下 git-cr-mana configure 才能配置到git中

- 在Windows下配置vscode作为git的默认编辑器，不能只使用code -w命令，而是需要使用 code.cmd -w