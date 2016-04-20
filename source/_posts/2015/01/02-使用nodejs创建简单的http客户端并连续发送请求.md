---
title: 使用nodejs创建简单的http客户端并连续发送请求
date: 2015-1-2
categories: Node.js
---
>新年之初，学院的网站上线了某个特别的页面，一个投票的页面，一点按钮就能计数。我想，与其一次一次地点他，为何不想办法简化呢。所以，想到了用nodejs建立客户端。


### 首先，使用http模块

最初的一步，当然是有http模块，使用这个模块，http服务器和客户端都可以实现。  
在http协议中，一个客户端应该做些什么事呢？往http服务器发送一个请求，等着服务器给你应答，他不应答就一直等着，你的请求没完他就一直等着。所以这里需要处理两个问题，如何发送请求，如何处理应答。

### 发送请求

这里使用http模块的request函数。形如：
```JavaScript
http.request(options, [callback])
```
第一个参数为选项，在里面可以设置hostname和path。第二个回调函数可选，形如function(res)，传进来的参数res是一个stream。虽说回调函数是可选的，为了实现不停点击，这个回调函数是必要的。  
request函数会返回一个ClientRequest对象(简称client)，request函数只会发送头部，而且不会发出整个request，如果要发出完整的，请使用client.write()和client.end()

### 处理应答

之前说起回调函数function(res)，当第一次收到应答时，该回调函数就会调用，但是，你只有一个stream，里面的内容还没拿到，在拿到数据之前就发起下一个request，他会当作你没有收到应答，所以，对这个stream一定要处置。  
怎么处置呢，当stream传完时，会发出data事件，所以用res.on('data', function())即可

### 完整代码
```JavaScript
var http = require('http')
var options = {
 hostname: "****",
 path: "/"
}
var func = function() {
  var req = http.request(options, function(res) {
    res.on('data', function(chunk){
    func()
    })
  })
  req.end()
}
func()
```
