---
title: git提交信息前添加分支名
date: 2016-11-13
categories: git
---
### 为什么要在提交中添加分支名
因为git不会在提交中存储分支，只有在合并时才会在提交信息中写入分支名，如果我是林纳斯，我早把这功能加上了。

### 如何添加
在你的项目中，找到`.git/hooks/commit-msg`文件（别跟我说没有，没有你自己建一个），在`commit-msg`中输入
```
#!/bin/sh
branch=$(git symbolic-ref HEAD -q --short)
msg=$(cat $1)
echo "$branch: $msg" > $1

```

### 解释原理
git在提交前，会先调用`commit-msg`，就相当于触发器、拦截器、task，随便你怎么说都行，但在这里叫hooks。

提交时，会把提交信息存在一个文件中，文件名作为第一个参数传入`commit-msg`，你只要读这个文件，就能读到提交信息，然后把分支名加上就行了。
