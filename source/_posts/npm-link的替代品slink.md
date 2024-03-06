---
title: npm-link的一个替代品slink
author: AyuLyt
date: 2024-03-06 16:28
updated: 2024-03-06 16:28
excerpt: metro打包时无法识别本地npm link的包怎么办
tags:
  - npm
  - link
---
在开发RN应用时，有时需要本地构建某个依赖包进行测试，但是metro打包时无法识别本地npm link的包，这里找到一个解决方案

https://github.com/tfennelly/slink

实际上就是将原本是软链接的依赖做成了文件依赖，然后启动一个服务定期监测文件变化，然后进行文件同步

根据此原理也可以自己开发一个，使用
- rsync
- chokidar
等即可