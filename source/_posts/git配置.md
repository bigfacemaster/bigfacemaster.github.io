---
title: git配置
date: 2017-04-06 20:57:58
tags: [git, git配置, GitHub]
category: git
---
> 当前环境: Ubuntu 16.04 LTS, GitHub

# git基本配置
* 与GitHub帐号关联
* 配置GitHub用户名：git config --global user.name "Github name"
* 配置GitHub邮箱： git config --global user.email email@email.com
* 配置自定义提交信息：git config --global commit.template ~/.gitmessage.txt

# git与GitHub相连
* 与GitHub的连接采用ssh方式：
```JavaScript
位于GitHub帐号下的设置里面
```
* 更改git的端口
修改 ~/.ssh/config 中 github.com 的配置 </br>
      Host github.com
      Hostname ssh.github.com
      Port 443


# git的基本操作
操作说明/描述
```JavaScript
* git pull --> 拉取github上面代码到本地
* git commit -a --> 提交本地代码到git本地缓存，并编写提交信息
* git push -->  讲本地提交的代码推送到服务器github
* git checkout --> 分之检查
```
```
检出分支并创建新的分支，切换到new_tree --> git checkout -b Test
提交到github  --> git push origin Test
设置分支上游追踪 --> git push --set-upstream origin develop
删除 --> git branch -d Test --> git push origin :Test
```
# 工具推荐
* 个人喜欢用命令行操作
* 对比工具 Meld
* 图形可视化Git工具：GitKraken
