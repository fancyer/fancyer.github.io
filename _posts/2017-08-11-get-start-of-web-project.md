---
layout:     post
title:      "web前端项目的基本概念"
subtitle:   ""
date:       2017-08-11 18:00:00
author:     "Fancyer"
header-img: "img/post-bg-2015.jpg"
tags:
    - JavaScript, web, 前端
---

## 基础环境

首先安装 node.js ：[官网下载](https://nodejs.org/en/download/)

安装 node.js 会顺带安装 npm ，这是前端项目的核心工具。

安装完成后，在终端/命令行运行 `node -v` 和 `npm -version` 验证是否安装成功。

> npm 的详细用法可以参照 [阮一峰的教程](http://javascript.ruanyifeng.com/nodejs/npm.html)。

前端项目用到的各种模块都需要通过 npm 安装，但由于墙的存在，下载模块经常不怎么顺利，所以需要另外一个工具：[nrm](https://github.com/Pana/nrm)。

终端/命令行运行 `npm install -g nrm` 全局安装nrm。安装成功后，运行 `nrm use taobao`切换为淘宝源。

> nrm 的详细用法参照其 [GitHub仓库的说明](https://github.com/Pana/nrm)。

---

## 项目结构

以vue提供的简单模板为例：

![project-structure](/img/in-post/post-startofweb/project-structure.png)