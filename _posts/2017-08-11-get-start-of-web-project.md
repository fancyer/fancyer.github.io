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

终端/命令行运行 `npm install -g nrm` 全局安装nrm。安装成功后，运行 `nrm use taobao` 切换为淘宝源。

> nrm 的详细用法参照其 [GitHub仓库的说明](https://github.com/Pana/nrm)。

---

## 项目结构

以vue提供的简单模板为例：

![project-structure](/img/in-post/post-startofweb/project-structure.png)

其中灰色的两个目录，项目初始的时候是不存在的。

* `dist` 目录下是编译过、用于发布的文件，编译源码后会出现。
* `node_moudules` 目录存放项目使用的模块资源，安装模块后会出现。

如果使用了git之类的系统，这两个目录要列入忽略列表。

* `src` 目录是主要的战场，我们编写的代码都在这里面。`src` 目录之下，会根据项目的具体需求，再建立子目录。如 components、vews、assets 等等。
* `package.json` 是npm生成的项目配置文件。[阮一峰的npm教程](http://javascript.ruanyifeng.com/nodejs/npm.html) 里有介绍，不再赘述。
* `webpack.config.js` 是打包工具 `webpack` 的配置文件。`webpack` 的用法可以参考其[官方教程](https://webpack.github.io/)。

---

## 建立新项目

constructing...

---

## 运行已有的项目

别人给的源码，或者从git上克隆下来的源码，是无法直接运行的，需要自己编译。仍然以上文的vue模板为例:

1. 终端/命令行 cd 进入项目的根目录；
2. 运行 `npm install` 自动安装需要的模块（配置在 `package.json` 里），这时候会自动建立 `node_moudules` 目录；
3. `package.json` 的 `scripts` 字段一般存放着打包、测试的命令，例如:
    ```
    "scripts": {
        "dev": "cross-env NODE_ENV=development webpack-dev-server --inline --hot",
        "build": "cross-env NODE_ENV=production webpack --progress --hide-modules"
      },
    ```
    运行 `npm run dev` 进行本地开发调试，`npm run build` 打包，集成了单元测试的项目还会有 `test` 命令。 
    
---

## 一些注意事项

* `npm install` 并不总是一帆风顺的。有时会因为网络问题，或者某个模块自身的问题，导致下载失败。可以通过切换下载源、手动下载安装包等方式来解决。

* 项目中用到的一些模块，可能需要其他的前置模块，有些前置模块需要用户自己预先安装。要仔细阅读npm的提示。

* 前端项目中常常使用 `sass` 或者 `less` . 其中 `sass` 依赖 `ruby` 语言环境，windows系统需要手动安装。
  * [下载 Ruby](https://rubyinstaller.org/downloads/)安装，安装时要勾选 `Add Ruby executables to your PATH`；
  * 安装之后，在开始菜单中找到ruby，打开Start Command Prompt with Ruby, 输入 `gem install sass`，回车确认；
  * 等待提示sass安装成功
  
> 安装 `sass` 也会遇到墙的问题，可参考[淘宝镜像安装sass](http://www.w3cplus.com/sassguide/install.html)