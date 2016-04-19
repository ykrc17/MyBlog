---
title: nodejs监听80端口(HTTP端口)
date: 2014-11-27
categories: Node.js
---
>这几天接触Nodejs下来，感觉颇深，要是大学有这门课就好了，大家也会去自发了解计算机网络方面的知识。这次使用Nodejs搭建简单的http服务器，并做出简单的”Hello World!”


### 方案1：Nodejs内置的http模块

用Nodejs，却不用模块，一定会被人笑话的。这次用最基本的http模块，过程很简单
```JavaScript
http = require 'http'
server = http.createServer (req, res) ->
        /*DO SOMETHING*/
server.listen 80
```
首先，引入http模块，再创建Server，进行监听。（别吐槽我的代码，这是coffeescript不是js）
会出现错误：events.js throw er;  
这是因为Linux中0-1023端口只允许root用户使用，所以要么使用其他端口，要么使用sudo node，当然你要root的话我也拦不住啊，自己承担后果吧。

### 方案2：express模块

使用express可以快速建立web应用，通俗点就是说“网站”。  
代码如下：
```JavaScript
express = require 'express'
app = express()
app.get '/', (req, res) ->
        /*DO SOMETHING*/
app.listen 80
```
express的监听默认使用http，所以还是用80端口吧。浏览器里每次使用url进行request，其实都是一次get，所以这里可以用get方法。  
但是这时又出现问题，sudo node提示找不到模块。这是因为，root的path与用户的不同，所以无法使用全局安装的模块了。这里不推荐去改secure_path，指不定被玩坏。还是老老实实把模块装到目录下吧，终端如下：  
```Bash
npm install express
```
