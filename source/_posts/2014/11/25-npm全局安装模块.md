---
title: npm全局安装模块
date: 2014-11-25
categories: Node.js
---
>第一次使用npm安装全局模块，本来以为会直接配置好环境变量的，但是npm有点不给力啊。


npm意为node package manager，用于管理nodejs的各种模块包，他的运行也依赖node，所以对系统底层的支持非常不好。  
最简单的例子，就是安装过程中，如果没有使用sudo，显示的是node中的err，而不是终端中的提示。

### npm安装模块

使用npm安装模块有两种方式
0. `npm install foo`  
这种方式会把模块包下载到当前目录
0. `sudo npm install foo -g`  
参数-g表示全局模块，安装在usr/local/lib/node-modules/下。

当使用node时，只会查看node_path和当前目录，所以如果没有配置环境，是没法使用全局安装的模块的。  
这时，只要在/etc/profile.d下新建一个.sh文件，
```Bash
export NODE_PATH=usr/local/lib/node-modules/
```
即可
