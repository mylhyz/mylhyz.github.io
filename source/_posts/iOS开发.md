---
title: iOS开发
author: AyuLyt
date: 2024-04-03 11:24
updated: 2024-04-03 11:24
excerpt: 一些开发iOS的入门文档
tags:
  - apple
  - macosx
  - ios
---

# 开发工具

- Xcode https://developer.apple.com/xcode/
官方IDE

- CocoaPods https://cocoapods.org/
包管理

- RVM https://rvm.io/
Ruby版本管理

- RubyGems https://rubygems.org/
Gem托管服务

- Bundler https://bundler.io/
管理Gem版本（CocoaPods也是一个Gem）

# 库

| 名称                                                              | 功能                        | 备注                   |
| --------------------------------------------------------------- | ------------------------- | -------------------- |
| [AFNetworking](https://github.com/AFNetworking/AFNetworking)    | 网络库                       |                      |
| [YYKit](https://github.com/ibireme/YYKit)                       | 一系列iOS开发库，包括图片，缓存，消息队列等功能 |                      |
| [GPUImage](https://github.com/BradLarson/GPUImage)              | 图片滤镜（比如对图片进行高斯模糊）         |                      |
| [ReactiveCocoa](https://github.com/ReactiveCocoa/ReactiveCocoa) | 响应式拓展库                    | 类似RxJava在Android中的地位 |

# 入门文档

| 文档                                                                                                                                                                   | 内容                                                                                                                                                                                                                                                                                            | 备注                                                                                                                                                                      |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [OC语言入门教程](https://www.runoob.com/w3cnote/objective-c-tutorial.html)                                                                                                 | 1. OC的方法调用相当于消息传递<br>    <br>2. 字符串使用<br>    <br>3. 类的定义 @interface，+表示类犯法，-表示实例方法<br>    <br>4. 方法定义<br>    <br>5. 属性声明<br>    <br>6. 协议定义 @protocol<br>    <br>7. 转发（方法调用相当于消息传递，如果一个类型不支持某些调用，可以转发给支持的类）<br>    <br>8. 类别 category，相当于类型拓展，一般 NSObject+String.h 这种命名的就是<br>    <br>9. 垃圾收集 |                                                                                                                                                                         |
| [OC基本数据类型](https://segmentfault.com/a/1190000005726614)                                                                                                              | 1. NSInteger<br>    <br>2. BOOL - YES/NO<br>    <br>3. CGFloat<br>    <br>4. NSString<br>    <br>5. NSValue（继承自NSObject）<br>    <br>6. NSNumber （继承自NSValue）<br>    <br>7. NSArray                                                                                                            | CG开头表示 Core Graphic（核心绘图），<br><br>一般都是定义在UIKit中而不是Foundation中<br><br>NSValue，NSNumber等和NSInteger等的不同之处在于，它们是类而不是基本类型。<br><br>因为NSInteger实际上是一个宏，映射到了long，而NSNumber确是一个类 |
| [官方文档-UIView](https://developer.apple.com/documentation/uikit/uiview?language=objc)                                                                                  | 1. 视图组件<br>    <br>2. 手势响应                                                                                                                                                                                                                                                                    |                                                                                                                                                                         |
| [官方文档-ViewController](https://developer.apple.com/documentation/uikit/uiviewcontroller?language=objc)                                                                | 1. 管理视图组件和层级                                                                                                                                                                                                                                                                                  |                                                                                                                                                                         |
| [使用纯代码写UI](https://blog.csdn.net/yuchu1900/article/details/80547791)                                                                                                 | 1. 使用ViewController和View<br>    <br>2. 使用代码编写UI<br>    <br>3. AutoLayout                                                                                                                                                                                                                      |                                                                                                                                                                         |
| [iOS布局方式概述](https://juejin.cn/post/6844903887703375880)                                                                                                              | 1. StoryBoard<br>    <br>2. AutoLayout/SnapKit/Masonry<br>    <br>3. Yoga等第三方                                                                                                                                                                                                                 |                                                                                                                                                                         |
| [官方文档-Info.plist使用](https://developer.apple.com/documentation/bundleresources/information_property_list/managing_your_app_s_information_property_list?language=objc) | 1. 一个k-v配置文件，可编辑                                                                                                                                                                                                                                                                              |                                                                                                                                                                         |
| [官方文档-管理App显示的内容（View Controller）](https://developer.apple.com/documentation/uikit/view_controllers/managing_content_in_your_app_s_windows?language=objc)            | 1. View Controller是管理View的，可以理解成广义上的容器<br>    <br>2. 导航（提供类似栈、线性、TabBar、Paged 效果的导航）<br>    <br>3. UIWindow下管理的是UIView的展示，并通过rootViewController关联了一个vc                                                                                                                                        | 1. 导航组件可以组合，嵌套使用<br>    <br>2. vc不属于UIView，不提供展示功能，只是作为视图的管理，这与Android中的Fragment/Activity的功能类似，特别是Window关联这部分跟Activity很像                                                |
| [新手教程-创建StoryBoard](https://developer.apple.com/tutorials/app-dev-training/creating-a-storyboard-app)                                                                | 1. 新手教程<br>    <br>2. 如何创建一个基于StoryBoard的App<br>    <br>3. 与StoryBoard对应的是SwiftUI                                                                                                                                                                                                             |                                                                                                                                                                         |
| [新手教程](https://developer.apple.com/tutorials/app-dev-training)                                                                                                       | 1. 官方提供的开发入门教程，包含了两个入门级APP的完整开发<br>    <br>2. SwiftUI的demo 和 UIKit的demo<br>    <br>3. 都是使用swift语言开发的                                                                                                                                                                                          |                                                                                                                                                                         |
| [iOS 9 Storyboard 教程(一上)](https://blog.csdn.net/yangmeng13930719363/article/details/49886547)                                                                        | 1. UI开发的入口，作为Scene的Storyboard是必须要了解的<br>    <br>2. 与ViewController绑定<br>    <br>3. TabBarController使用                                                                                                                                                                                         |                                                                                                                                                                         |
| [iOS 9 Storyboard 教程(二上)](https://www.jianshu.com/p/0ec8d6314791)                                                                                                    | 1. Segue - 导航                                                                                                                                                                                                                                                                                 | 后续文档 [iOS 9 Storyboard 教程(二下)](https://www.jianshu.com/p/df8ab9c872ec)                                                                                                  |
