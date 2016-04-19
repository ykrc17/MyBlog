---
title: 为Ubuntu安装jdk
date: 2014-11-10
categories: Java
---
>电脑新装了Ubuntu，需要把以前的开发环境都换一遍。在安装AS的时候，遇到了需要jdk的问题


### 方案一：openjdk

openjdk是sun于07年发布的开源jdk，因为其开源，所以能在ubuntu社区中找到，安装方式也十分方便。

安装方式：  
0. 打开terminal
0. 运行`sudo apt-get install openjdk-8-jdk`

没错，就是这么简单，只要一行命令。openjdk除了openjdk8外，还有6与7版本，以供选择。

但是他也有局限性，openjdk6是sun在07年发布的，但是java7于2011年发布时，sun已经被oracle所收购，java7的一部分为oracle编写的，那一部分代码没有开源，不能放入openjdk。也就是说，10年后openjdk的一部分是缺失的。  
为了关键时刻不出岔子，还是装一个oracle-jdk比较稳妥。

### 方案二：oracle-jdk

0. 去oracle官网下载jdk：[地址](http://www.oracle.com/technetwork/java/javase/downloads/index.html)
0. 下载好压缩包，提取到任意位置。
0. 在/etc/profile.d目录下加入新的脚本。该目录会在每次开机时自动执行目录下的所有脚本。
脚本内容如下，后缀名.sh
```Bash
export JAVA_HOME=爱填啥填啥
export JRE_HOME=$JAVA_HOME/jre
export CLASSPATH=.:$JAVA_HOME/lib:$JRE_HOME/lib:$CLASSPATH
export PATH=$JAVA_HOME/bin:$JRE_HOME/bin:$PATH
```
0. 重启后执行命令
`java -version`
查看是否配置成功
