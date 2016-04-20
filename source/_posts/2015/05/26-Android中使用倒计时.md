---
title: Android中使用倒计时
date: 2015-5-26
categories: Android
---
>在项目中遇到了问题：发送短信验证码，如何限制一分钟发送一条。

### 方法一

使用Handler的postDelayed方法。

该方法我也用在nodejs项目中，在一个runnable结束时再调用一遍，就能实现循环

### 方法二

使用`CountDownTimer`。

这是android自带的倒计时工具。既然能少些点儿代码，何乐不为呢。

用法类似于AsyncTask，十分方便。
