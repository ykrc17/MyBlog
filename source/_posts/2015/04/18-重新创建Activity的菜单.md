---
title: 重新创建Activity的菜单
date: 2015-4-18
categories: Android
---
>问题描述：
今天在MainActivity中加入了四个标签页，想给每个标签页分配不同的ActionBar按钮，这该如何是好。


### 小知识点1

ActionBar中的按钮，是在menu中设置的。记得给item加上`showAsAction:always`。

### 小知识点2

这次要介绍Activity的两个函数：`onCreateOptionsMenu`和`onPrepareOptionsMenu`。
- `onCreateOptionsMenu`会在菜单创建前调用。
- `onPrepareOptionsMenu`会在菜单显示前调用。

### 问题解决方法

Activity还有一个方法：`invalidateOptionsMenu`。

调用该方法，就会调用`onCreateOptionsMenu`。所以，切换了标签页后，调用`invalidateOptionsMenu`方法即可。
