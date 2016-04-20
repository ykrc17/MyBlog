---
title: phpMyAdmin遇到问题，无效的令牌
date: 2015-1-31
categories: PHP
---
>这几天做网站的时候，需要用到MySQL，装上xmpp却不能用phpMyAdmin，以前有个登录框，现在却没了，显示“无效的令牌”


在网上看到一个搞笑的说法，把“phpMyAdmin”改成“phpmyadmin”就行了，我从未见过如此厚颜无耻之人，竟说出如此粗鄙之语。。。

实际方法是，进入phpMyAdmin目录下的config.inc.php，有一条设置auth_type，有三种常用的，分别是“config”，“cookie”，“http”。

- config是从config.inc.php文件中读取用户密码，不够灵活，不推荐
- cookie是从浏览器登录，将登陆信息写入cookie。
- http是弹出一个登录框，让你输入信息。

将auth_type从config改为cookie之后，就成功了
