---
title: ECMAScript5特性-迭代器与生成器
date: 2016-3-7
categories: JavaScript
---
>今天随便翻东西，翻到了function*()。这个函数后面竟然有个星号，莫非是指针？抱着怀疑的心态，上网查到了迭代器和生成器。

### 迭代器(iterator)

第一次听到迭代器，还是在学习C++的时候。当时学到List这个概念，List是一个线性的存储结构，他需要一个方法，来遍历里面的内容。当时有两种方法，一个是用for循环，用索引遍历；另一个就是迭代器。  
迭代器，指向List中的某一个元素，当调用迭代器的next()方法时，指向并返回下一个元素。  
在ECMAScript中，迭代器的功能更为恐怖，他会遍历对象(不只是List)中的每一个元素。每一个对象的元素，都会被返回。

### 简单的JSON对象
```JavaScript
var me = {name:"yk",age:21}
var it = Iterator(me)
```
it即为me对象的迭代器，it.next()依次返回name:”yk”、age:21，第三次则会报错。

### Array
```JavaScript
var arr = ["jiang","hu","xi"]
var it = Iterator(arr)
```
it.next()会返回1:”jiang”、2:”hu”、3:”xi”

### function*

对，你没听错，迭代器能让函数返回多个值！这已经颠覆三观了。  
当然这里的函数跟一般函数不同，我们称他为生成器(generator)，生成器能返回多个值，他会生成一个迭代器，能使用到所有返回值。
```JavaScript
var gen = function*(){
yield 1
yield 2
}
var it = gen()
```
it.next()会依次返回1、2，这里的function即表示生成器，调用function()会生成迭代器。
yield会使函数内的操作暂停，直到再次调用it.next()
