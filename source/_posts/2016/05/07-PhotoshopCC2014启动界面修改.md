---
title: Photoshop CC 2014启动界面修改
date: 2016-5-7
categories: 软件
---
### 起因
前几天刷微博的时候，看到平板姬的这条[微博](http://weibo.com/2029177923/Dsq44uUxN)：

![](/images/2016-5-7.01.png)

联想到自己的PS CC的官方启动界面太过文艺，不符合本大爷的口味，所以心血来潮，想要给PS的启动界面换个血。

### 经过
PS CC 2014，被一些人称作PS 15，这实在是太有迷惑性了，找到一个自称适用于PS 14的启动界面修改工具，结果根本改不了PS CC 2014，在找工具的时候就走了不少弯路。

之后在google上找到了国际友人提供的工具，可以修改PS CC 2014，使用方法如下：
0. 下载工具，并解压
0. 打开PS的安装目录，将Resources目录拷贝至工具的pscc2014Icon目录下
0. 运行`Extract.cmd`，等待提取完成
0. 找到提取文件中High和Low目录中的`SplashExtendedBackground_s0.png`。`SplashBackground_s0.png`不会影响启动界面，所以可以不用修改。  
![](/images/2016-5-7.02.png)
0. 将自己的图片放入`SplashExtendedBackground_s0.png`，以PS CC 2014为例，需要把自己的图片大小调整为`1484*788`  
![](/images/2016-5-7.03.png)
0. 运行`Pack.cmd`，将打包好的Resources目录替换PS安装目录中的Resources目录
0. Enjoy

### 结果
![](/images/2016-5-7.04.png)

### 工具下载
自古江湖流传着“留图不留种，菊花万人捅”的规矩，为了保住菊花，自然要附上链接了。

Photoshop CC Splash Screen Extractor：  
[下载地址](http://rgho.st/8p5dL66JY)  
[原文链接](https://www.youtube.com/watch?v=cHkeFfzyw_o)
