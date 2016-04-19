---
title: JavaScript：使用js控制台，引用外站*.js文件
date: 2014-9-13
categories: JavaScript
---
### 动机

在跟学校形势政策考试斗智斗勇的过程中，遇到一个问题，如何更加方便的调用答题器，而不用每次都在控制台里复制粘贴。于是，想到了从控制台中引用*.js文件。

### 原理

在html中引用外部.js文件，必须要在html中有一个script元素，并把src属性设置为外部.js文件的地址。但是问题是，控制台里只能输入js代码，又如何创建script元素呢。
这里用到document.createElement()方法，这个方法能够创建一个元素对象，创建完后再利用appendChild()或insertBefore()插入到指定节点。

### 用createElement()创建script元素
```JavaScript
var body = document.getElementsByTagName('BODY').item(0);
var element = document.createElement("script");

// 外部方式
element.src = ****;
// 内部方式
element.innerHTML = ****;

body.appendChild(element);
```
如上代码将js代码插入到body元素的末尾。
该段代码可以在控制台中使用，比以前整个答题器的代码放入控制台来说，轻松多了。
