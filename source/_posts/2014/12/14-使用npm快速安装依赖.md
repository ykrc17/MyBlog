---
title: 使用npm快速安装依赖
date: 2014-12-14
categories: Node.js
---
因为种种原因，不得不将一个项目放在两台电脑里。这时遇到了一个问题，电脑A中已经配置好了express等模块，电脑B中还没有，我是不是该一个一个模块去装呢。其实，有个简便方法。

### 使用npm安装模块

首先从简单的问题开始谈起，如果要安装一个nodejs模块，该怎么办？
使用命令：
```Bash
npm install *模块名*
```
即可，可以选择使用参数-g，使用后会安装在用户的文件夹中，不使用则会安装到./node_modules目录下。

### install指令中，不指定模块，又会如何

install指令，一看就需要指定模块，你不指定，叫我安装个毛啊。  
但是npm就是这么奇葩，npm install是可以执行的。该命令的功能是，根据目录下package.json文件的内容，安装模块。  
就是说，package.json中标明了的模块，都会被安装。  

### package.json文件示例

这里给出一个最简单的package.json文件，用于安装express模块。
```JSON
{
    "dependencies" : {
        "express" : "*"
    }
}
```
既然是json文件，整个就是个对象，把需要的模块写在dependencies模块中即可。

### package.json其他属性

这里列出几个常用的，其他的请去官网查看[官方文档](https://docs.npmjs.com/files/package.json)。

- name – 项目的名称
- version – 版本号
- description – 项目描述
- homepage- 项目主页
- author – 作者
- repository – 版本库
