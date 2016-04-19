---
title: mongodb在ubuntu上的安装
date: 2014-12-22
categories: Linux
---
>这几天在考虑给我的小破网站加个数据库，既然是基于nodejs的网站，给他配个同一家族的得了，顺便学习一下mongodb。

### 1、安装

安装可以使用最简单最常用的apt-get。
使用以下命令
```Bash
sudo apt-get install mongodb
```
社区的版本比较旧，也可以使用mongodb的官方源，因为这里难度为Lv.0，所以不多说了。

### 2、配置

你如果以为安装完就万事大吉，可以开始跑了，那就大错特错了。在运行之前还需要配置mongodb的存储位置。安装时候不帮你配置还，一看就是用着javascript的。  
默认的位置是/data/db。这个位置在ubuntu下访问、更改时需要管理员权限的。当然，你也可以不用默认位置。  
方法就是运行以下命令：  
```Bash
sudo mkdir /data
sudo mkdir /data/db
```
之后就可以运行了。

### 3、运行

运行可以说是最简单的一步了。  
服务端用mongod，客户端用mongo即可。
