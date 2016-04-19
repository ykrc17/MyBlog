---
title: 将菜单加入ActionBar
date: 2014-9-22
categories: Android
---
> 现在很多安卓应用在ActionBar最右侧都有个“溢出按钮”，非常方便。这次学习了如何将菜单项与菜单加入ActionBar。

### 加入菜单项

在`res/menu`目录下，在`*.xml`文件中，可以给item标签添加`android:showAsAction`属性，值为`ifRoom`，菜单项就会加入ActionBar

### 加入子菜单

在已经添加`android:showAsAction`属性的item中，再添加一个menu子元素，即可实现在
