---
title: Zazu-Launcher移植到新版本Electron
author: AyuLyt
date: 2024-07-22 17:38
updated: 2024-07-22 17:38
excerpt: 日常需要一个简单的类Alfred工具，但是开源方案都不是很喜欢，zazu是调研时发现的挺喜欢的一个工具，但是很久没更新了，因此尝试为它更新到最新版的electron
tags:
  - zazu
  - launcher
  - cross-platform
  - open-source
  - electron
---
由于原始代码大量混杂renderer和main等的使用，在新架构下水土不服，暂时不继续进行移植，

##### 1.renderer进程不再支持调用require

也就是说html文件引用的代码不能使用require，因此需要将代码打包成独立的js文件




# 附录

##### 1.electron进程间通信

 https://www.electronjs.org/zh/docs/latest/tutorial/ipc

- main进程，执行node代码的进程，使用NodeJS接口，可以通过preload脚本向renderer进程发送消息
- renderer进程，执行html渲染的进程，使用浏览器DOM和BOM接口，只能通过preload脚本暴露相关方法来与main进程通信

main.js 是主进程脚本
- 使用node，electron相关API
preload.js 是预加载脚本
- 使用node，electron相关API
renderer.js 是渲染进程脚本
- 只能使用DOM相关API和通过preload暴露到window下的接口

main.js 
- 访问 ipcMain，可以通过on接收，send发送消息
- 通过handle响应回调处理
preload.js
- 访问 contextBridge，ipcRenderer，可以通过on接收，send发送消息
- 通过invoke调用main进程的API