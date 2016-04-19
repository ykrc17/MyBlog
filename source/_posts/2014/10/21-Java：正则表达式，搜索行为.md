---
title: Java：正则表达式，搜索行为
date: 2014-10-21
categories: Java
---
> 正则表达式中有三个标志，可以指定搜索行为。这次来分别介绍一下

### 三种标志

- 标志g  
global，全局标志，会匹配全文中所有符合的匹配
- 标志i  
ignore case，无视大小写
- 标志m  
multible，多行

### 使用方法

(?i)表示开始  
(?-i)表示结束<可选>  
例：(?i)book 可以匹配 BoOk  
