---
title: 给express带个session
date: 2014-12-25
categories: Node.js
---
>用过PHP的人都知道session吧。和cookie相同，都能用户存储访问的数据，但是session比cookie更加安全、可靠，那是因为cookie存在本地，而session存在服务端，你总不能乱改session吧。


### 中间件express-session

这是express自带的中间件，可以实现简单的session功能，使用起来也非常方便。
```JavaScript
var session = require('express-session')
app.use(session({}))
```
这样就完成了中间件的使用。  
session还有一些参数可以设置，在这里可以查看：地址

### session的使用

session的使用也非常简单，直接使用req.session即可
