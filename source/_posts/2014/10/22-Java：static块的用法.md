---
title: Java：static块的用法
date: 2014-10-22
categories: Java
---
> 平时使用static关键字时候，动机很单纯，这个类里需要一个全局常量。这个常量如果是基本类型还好，如果是某个类呢。这时，可以用static块对全局常量进行初始化


### static块

static块内的代码，在类被第一次加载、并且所有static常量初始化完成后，被执行。  
static块只在类被加载时执行一次，之后不会再被执行。  
多个static块会按照顺序执行，互相之间并无冲突。  

### 例子

类中有全局的ArrayList，里面存有3个Integer，分别是1、2、3。

```Java
public static final ArrayList<Integer> INTEGER_LIST;
static {
  INTEGER_LIST = new ArrayList<Integer>();
  INTEGER_LSIT.add(1);
  INTEGER_LSIT.add(2);
  INTEGER_LSIT.add(3);
}
```
这样就完成了对INTEGER_LIST的初始化。
