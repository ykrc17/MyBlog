---
title: AndroidSDK下载方法
date: 2015-3-21
categories: Android
---
>要开发Android，就必须要有Android SDK。要下载Android SDK，就必须连到google。现在google没法上，那是不是没法开发了？


### 1、过去方法

曾经有一个学校的镜像站，提供了Android SDK的镜像，他名为东软开源镜像站。  
全中国那么多学校，那么多开源镜像站，为什么就他个小破学院能有android sdk？有两种可能性，一是，东软学院买了国内Android SDK的版权，二是，他是一个傻逼，根本就不管自己有没有版权。
我认为后者的情况更可能发生。但是不管如何，先用了再说。

步骤：

0. 设置http代理：  
`mirrors.neusoft.edu.cn:80`
0. 勾上强制http，即可。
### 2、google未死

google真的上不去了么，非也，我们还是能FAN墙上谷歌的。  
既然能上google，就能去android官网下一个sdk。这时，出现了个奇怪的问题，android官网必须要FAN墙，但是从官网下sdk，不需要FAN墙。  
这是什么意思呢，ZF只屏蔽了google的web服务而已，google的文件服务没有被屏蔽，所以，只要派人去官网拿个下载链接，大家都能下了。  

步骤：

0. FAN墙，上developer.android.com
0. 找个链接，停止FAN墙，开始下载
### 3、再见吧，东软

这几天不知咋的，东软镜像站慢的像狗一样。那也无所谓了，这种小学院咱才没兴趣呢，反正只要上得去android官网就行了。  
同理，Android SDK Manager也可以同样使用。

步骤：

0. FAN墙，然后Packages->Reload
0. 停止FAN墙，开始下载

是不是 省力又省心？
