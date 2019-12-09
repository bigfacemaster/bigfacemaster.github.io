---
title: Mac-Finder-show-path
date: 2018-03-08 13:57:37
tags: Skills
category: SKills
---

Finder默认是不显示路径的，进入某个文件夹时只会显示当前文件夹的名字。

通过下面的命令可以在finder顶部的标题栏上显示完整路径。

在终端输入以下命令并回车：

defaults write com.apple.finder _FXShowPosixPathInTitle -bool YES

把finder关了再打开，在标题栏中即可显示文件的完整路径，而且对着路径最左边的小图标点右键，就能快速访问路径中的任意一层。
