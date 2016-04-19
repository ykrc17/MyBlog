---
title: WordPress：主题的翻译
date: 2014-9-9
categories: PHP
---
WordPress预装了3款主题，并且官网有丰富的主题资源供下载。但是，预装的主题没个性，官网的主题没汉化。所以，只能自给自足，翻译主题吧。

### WordPress翻译的原理

WordPress为了支持多国语言，使用了gettext函数库。gettext函数库支持多种编程语言，当然包括PHP，所以WordPress才能使用它。
gettext处理的文件有两种，`*.po`与`*.mo`，前者是源代码，后者是机器码，翻译者要做的工作就是编辑源代码，然后编译成机器码，供程序使用。

### 准备工作

下载[Poedit](https://poedit.net/)，看他名字就知道，是用来编辑`*.po`文件的编辑器。
从主题中获取原版`*.po`文件，位置为`wp-content/themes/*你的主题*/languages/`。

### 进行翻译

翻译过程很繁琐，这里就不多说了，文件保存为`zh-CN.po`。
Poedit在编辑完成后，会自动编译`*.mo`文件，之后将两个文件上传，就大功告成
