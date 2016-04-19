---
title: 模仿FAB制作悬浮按钮
date: 2014-11-14
categories: Android
---
>Android 5.0新增了悬浮按钮(Floating Action Button)的特性，例如，在一个通讯录悬浮着一个“新增”按钮，表明新增联系人，非常醒目。这里，我们尝试模仿一个悬浮按钮。


### 一、布局

悬浮按钮，悬浮就是他的一大特色。为了实现悬浮，就要在布局上做文章。  
布局父元素应该是RelativeLayout或AbsoluteLayout，后者过于落后，可以无视。  
利用RelativeLayout将他固定到右下角即可。  

### 二、外观

悬浮按钮的外观有两个要求：1、圆形，2、阴影。圆形可以用shape实现，但是阴影呢？  
这里，我们使用新出的`CardView`，允许使用圆角，自带阴影，是不错的选择。
```XML
xmlns:app="http://schemas.android.com/apk/res-auto"
android:layout_width="48dp"
android:layout_height="48dp"
app:cardCornerRadius="24dp"
app:cardPreventCornerOverlap="false"
```

这样大概就可以了。最后的`preventCornerOverlap`默认设置为true，设置为false可以将`CardView`内部撑满。

### 三、触摸反馈

既然是一个按钮，那么按下去时必须要有反馈。这里我们使用selector，为通常状态与按下状态分别分配一个按钮的背景。  
一个状态设置`android:state_pressed="true"`属性，另一个则相反。  
最后往内部加入几个图案，一个悬浮按钮就完成了。
