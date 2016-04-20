---
title: 在Windows上将mongod设为服务
date: 2015-1-12
categories: Windows
---
>之前在ubuntu上安装mongodb，安装完就自动完成配置，也不需要将他设为服务。但是windows上似乎麻烦一点，需要自行安装为服务，隔壁的mysql就客气多了。


### 安装准备

最重要的一步，确定你安装好了mongodb。  
将mongo和mongod加入path，当然，只要把mongo根目录下的bin文件夹加入path就行了。
### 安装过程

这里使用mongod命令，注意以下几点：

0. 需要设置db的路径，使用参数—dbpath，该路径上的文件夹一定存在（需要手动创建）
0. 需要设置log的路径，使用参数—logpath，该文件会自动创建

命令如下：
```
mongod --dbpath c:\foo\db --logpath c:\foo\bar.log --install
```
### 结束后的事项

安装完成后，第一次启动需要手动开启，或者重启系统。  
需要重新安装，请使用参数—reinstall
