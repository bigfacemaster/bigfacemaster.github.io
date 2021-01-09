---
title: git merge vs rebase
date: 2021-01-09 17:56:18
tags: [ARTS, Share, git]
category: [ARTS]
---

# git merge vs rebase



> 背景：在git pull会显示如下
>
> ![git merge vs rebase](http://bigfacemaster.test.upcdn.net/uPic/sZVajS.png)
>
> 于是产生了想要弄清楚他们三个的区别。



> git pull === git fetch + git merge (默认)
>
> git pull —rebase === git fetch + git rebase



## git rebase

此命令会将远程目标分支的代码下载下来，然后与本地的代码合并，然后推送到目标远程分支，此操作不会产生新的提交日志。

如果遇到了冲突，那么需要先将冲突解决掉，然后**git rebase —continue**，会一个个冲突的解决，知道解决完成，将目标代码推送到远程分支。



![使用rebase合并分支](https://backlog.com/git-tutorial/cn/img/post/stepup/capture_stepup1_4_8.png)

## git merge

此命令会将远程目标分支的代码下载下来，然后与本地的代码合并，然后推送到目标远程分支，此操作会产生新的提交日志，一般是**Merge Branch xxx**。

如果遇到了冲突，需要一次性将所有冲突解决掉，然后再推送分支到远程。

![结合了两个修改的合并提交](https://backlog.com/git-tutorial/cn/img/post/stepup/capture_stepup1_4_4.png)

## git fast forward

此命令合并之后，只能看到有记录合并到目标分支，而看不到具体的内容。



所以我个人是比较喜欢使用**git merge** ，更加的熟悉与得心应手。亦可看到每个的具体分支，方便以后直接从某个分支记录切出分