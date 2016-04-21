---
title: JVM语言Kotlin正式发布
date: 2016-2-19
categories: Kotlin
---
>JVM语言Kotlin在2016.2.15发布了他的第一个正式版本1.0，Kotlin弥补了Java的一些缺陷，比起Java更加简单，并且引入了一些函数式语言的特性。接下来就具体介绍一下Kotlin

### Kotlin是一种JVM语言

JVM语言有很多，他们都是Kotlin的前辈，比如Groovy、Clojure、Scala
所谓JVM语言，就是编程语言不是Java，但是编译出来的字节码可以在JVM中运行。但是明明都是在JVM里运行，性能再高也高不过Java，那这些JVM语言为什么出现呢，有以下原因：

- 不用写运行环境，直接用JVM就行，而且JVM的性能经过这些年的优化，已经有长足进步
- Java语法太过复杂，我觉得每个表达式的分号简直多余
- Java有一些缺陷，比如所有人都遇到过的空指针问题，我觉得这问题能跟stackoverflow相提并论了
- 一些新的语言特性，比如函数式编程，Java中还没有普及

当然，一款优秀JVM还需要编写Java和自己之间的语言桥，这样就可以使用现有的大多数Java库了


### 关于Kotlin

Kotlin是JetBrains（简称JB）开发的语言，JB旗下还有诸多IDE，其中有Java开发环境Intellij IDEA。既然是自家的IDE，自家的语言，IDEA内置Kotlin插件也是理所当然，下载运行IDEA，就可以创建Kotlin项目了  
IDEA被誉为最好的Java开发环境（曾经是Eclipse），世界各地都有使用IDEA的开发者，凭借IDEA庞大的的使用者数量，就知道Kotlin有一定的优势  
Kotlin的主要竞争对手是Scala，有一部分Java特性，也有一部分函数式编程的特性，属于混合式语言。一方面，Scala因为先出山，所以较为成熟；但另一方面，Kotlin有IDEA的加持，有比Scala更简洁的语法，跟Java有较高的兼容性，相信Kotlin未来一定大有作为

### Kotlin的一些语法

### 1、Hello Kotlin!

版本1：
```JavaScript
fun main(args : ArrayList<String>) {
 println("Hello Kotlin!")
}
```
- 类型在变量名的后面
- 函数用fun表示
- 表达式后不一定要有;，你看我这篇文章每段最后都懒得写句号，代码里分号我也肯定是不会写的

版本2：
```JavaScript
fun main(args : ArrayList<String>) = println("Hello Kotlin!")
```
- 当函数里只有一句表达式时，可以用等号取代大括号

### 2、默认参数

我先写一个函数，可以把两个数相加，返回他们的和
```JavaScript
fun sum(a : Int, b : Int = a) : Int = a + b
fun sum(a : Int, b : Int = a) = a + b
```
- 当你不传参数b的时候，b会是a
- 这Int相当于Java里的Integer
- 上下两句是一样的，单表达式用等号的情况下，你不写返回值的类型，Kotlin编译器会自己判断返回值

### 3、指定参数

我现在调用这个sum函数
```JavaScript
sum(1, 2) // 结果为3
sum(a = 1, b = 2) // 结果为3
sum(a = 1) // 结果为2
```
你可以在调用时指定参数名
### 4、高阶函数和lambda表达式

高阶函数是什么意思，就是这个高阶函数，他的参数可以是函数，他的返回值类型可以是函数  
什么又是lambda呢，就是长得像(x: Int, y: Int) -> x + y这样，表示参数为x和y，返回值为x+y的匿名函数
```JavaScript
fun doSomething(a : Int = 0, something: (Int) -> Int) : Int {
 return something(a)
}
```
我这是举个例子，现实中可没有这么蠢的函数

- 这里something，他的类型是一个参数为Int，返回值为Int的函数

我们给他传参
```JavaScript
doSomething(0, {a -> a * 2})
doSomething(0, {a * 2})
doSomething(0, {it * 2})
doSomething{it * 2}
```
- 这三句话是一样的结果
- 当lambda只有一个参数的时候，可以省略参数
- 当函数只有一个参数， 且那个参数是lambda时，可以省略括号
### 5、匿名函数

上一题除了用lambda表达式，还可以用匿名函数
```JavaScript
doSomething(0, func(a: Int): Int {return a * 2})
doSomething(0, func(a: Int) = a * 2)
```
Java里面可没有匿名函数，只有匿名对象，在Java里顶多new一个Runnable来当匿名函数

### 6、字符串
```JavaScript
func hello(data: String) = "Hello ${data}!"
println(hello("Kotlin"))
```
输出结果为Hello Kotlin!

在字符串中，可以使用$作为占位符，大括号可以省略

当然这些只是部分特性，大家可以先试着用起来了，安装Intellij IDEA就直接能用Kotlin哦
