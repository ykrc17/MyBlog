---
title: Apache创建虚拟主机(virtual host)
date: 2015-3-10
categories: PHP
---
>什么叫虚拟主机呢。买过万网的虚拟主机不，就是那种感觉。给你分配一个内网的ip，然后给你划个www空间，就完事了。这里介绍最简单的配置方式


### 启用vhost模块

打开文件`conf/httpd.conf`，找到一下行
```XML
# Virtual hosts
Include conf/extra/httpd-vhosts.conf
```
如果Include前有#，则去掉

### 配置vhosts

打开文件`conf/extra/httpd-vhosts.conf`，新建vhost
```XML
<VirtualHost <主机ip>:80>
 DocumentRoot "<你的路径>"
 <Directory "<你的路径>">
 Require all granted
 </Directory>
</VirtualHost>
```
有以下注意事项：

- 主机ip第一字段，必须为127，例如127.1.2.3，但不能是128.1.2.3
- 上下两个路径必须一样（废话）
- 之前有人说，把httpd.conf里的require all denied去掉，这样就能用了。我不同意，这样别人就能访问你的服务器的所有文件了。这里，只在VirtualHost里加上文件权限，更为安全。
