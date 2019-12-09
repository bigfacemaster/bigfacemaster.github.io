---
title: git设置fork的上游
date: 2017-09-15 17:22:32
tags: git
category: git
---
# 说明
* Lfork 为fork到自己的仓库的项目名称
* Lupstream 为你从哪里fork过来的源项目的名称
# 具体操作如下
```
// 从GitHub克隆代码到本地
git clone git@github.com:leejay1992/Lfork.git
Cloning into 'Lfork'...
remote: ...
➜ cd Lfork
// 查看
➜  Lfork git:(master) git remote -v
origin	git@github.com:leejay1992/Lfork.git (fetch)
origin	git@github.com:leejay1992/Lfork.git (push)
// 设置追踪上游
➜  Lfork git:(master) git remote add upstream git@github.com:Lupstream/Lupstream.git
➜  Lfork git:(master) git remote -v
origin	git@github.com:leejay1992/Lfork.git (fetch)
origin	git@github.com:leejay1992/Lfork.git (push)
upstream	git@github.com:Lupstream/Lupstream.git (fetch)
upstream	git@github.com:Lupstream/Lupstream.git (push)
// 保持代码与上游项目相同
➜  Lfork git:(master) git fetch upstream
From github.com:Lupstream/Lupstream
 ...
➜  Lfork git:(master) git merge upstream/Lupstream

```
