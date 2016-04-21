---
title: 使用Hexo和GithubPages搭建博客
date: 2016-4-21
categories: 互联网
---
>最近把之前的博客迁移到GithubPages这边，以后就不用付服务器的年租费了。本文就讲讲怎么通过Hexo和GithubPages搭建博客的

### GithubPages
GithubPages类似于github中以raw的方式访问仓库中的文件，允许你通过http的方式访问该仓库中的文件。但是跟raw不同，raw不会设置content-type，所以打开html文件会显示源码，而githubPages打开html文件，会打开网页。

### 创建GithubPages
0. 打开github
0. 创建一个名为`{你的用户名}.github.io`的仓库
0. 在地址栏里`http://{你的用户名}.github.io/`就能访问你的githubPages了

### Hexo
Hexo能够把你编写的markdown（或是其他）文件，生成为html网页，虽然比起在线的编辑器要弱一点，但是由于不需要任何后端代码，是生成的静态文件，所以可以部署在各种服务器上。  

Hexo主要由四部分组成：
- Hexo库  
通过源文件和主题生成网页
- 配置文件  
根目录下的`_config.yml`，配置整个站点的信息
- 主题  
决定了整个博客的式样和交互方式
- 源文件  
用来编写博客的markdown文件

### 使用Hexo编写博客
0. 安装npm和git，Windows可以安装Node.js，安装git需要把git加入PATH
0. 运行`npm install hexo-cli -g`
0. 进入你想存放博客源文件的目录，运行`hexo init <文件夹名>`。  
如果你已经有hexo博客源文件，那么进入博客目录，运行`npm install`
0. 写一篇文章
0. 在`_config.yml`中进行部署的设置
0. 如果没安装hexo-deployer-git，运行`npm install hexo-deployer-git --save`
0. 运行`hexo deploy -g`

### 一些命令
- `hexo deploy -g`和`hexo generate -d`都是生成后再部署
- `hexo clean`可以删除public目录  
虽然我觉得还不如`rm public -r`
- `hexo deploy`在public目录为空的时候，会进行生成
