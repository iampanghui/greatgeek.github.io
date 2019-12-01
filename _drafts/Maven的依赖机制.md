---
layout:     post
title:	Maven 的依赖机制
subtitle:   
date:       2019-11-28
author: 	庞晖
header-img: img/post-bg-ios9-web.jpg
catalog: 	 true
tags: 	构建工具
---

### Maven的依赖机制介绍
[Introduction to the Dependency Mechanism](http://maven.apache.org/guides/introduction/introduction-to-dependency-mechanism.html)

摘自Maven官网:

Dependency management is a core feature of Maven. Managing dependencies for a single project is easy. Managing dependencies for multi-module projects and applications that consist of hundreds of modules is possible. Maven helps a great deal in defining, creating, and maintaining reproducible builds with well-defined classpaths and library versions.

### 对比传统方式与Maven管理依赖
假设你的项目需要 Log4J 来作为你的项目登录机制.
#### 传统方式
1. 访问 http://logging.apache.org/log4j
2. 下载 Log4j jar 包
3. 复制该jar 包到项目的 classpath下
4. 手动给项目添加依赖
5. 你需要做所有的事

**Windows 下还有一部分, 加起来才完整**