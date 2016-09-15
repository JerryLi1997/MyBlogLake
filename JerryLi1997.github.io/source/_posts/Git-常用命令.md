---
title: Git 常用命令
date: 2016-09-14 20:24:51
categories:
- instructions
tags:
- git
description: "Git 中使用频率较高的命令。"
---

# Git

### 安装 Git

```
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
```

### 创建版本库

`git init` 命令把当前目录变成 Git 可以管理的仓库。

不要使用 Windows 自带的记事本编辑任何文本文件。

`git add` 命令将文件添加到暂存区。

`git commit` 命令将改动提交到当前分支。`-m "*"` 参数增加提交说明。

### 版本管理

`git status` 查看仓库当前状态。

`git diff` 查看 difference。

`git log` 显示从最近到最远的提交日志。`--pretty=oneline` 参数减少输出信息。

`git reset --hard HEAD^` 回退到上一个版本。

`git reset --hard *` 回退到某个版本，* 为版本号。

`git reflog` 查看每一次命令。

`git checkout -- file` 丢弃工作区对某文件的修改。用版本库里的版本替换工作区的版本。

`git reset HEAD file` 撤销暂存区的修改。

`git rm file` 从版本库中删除文件。

### 远程仓库

`ssh-keygen -t rsa -C "youremali@example.com"` 创建 SSH Key。

`git push -u origin master` 把本地库的内容推送到远程，`-u` 参数会把本地的`master` 分支和远程`master` 分支关联起来，以后推送或者拉取可以简化命令。

### 分支管理

`git checkout -b dev` 创建`dev` 分支并切换，`-b` 相当于`git branch dev` 和`git checkout dev` 。

`git branch` 查看分支。

`git merge dev` 合并` dev` 分支到当前分支。

`git branch -d dev` 删除`dev` 分支。

`git log --graph` 可以看到分支合并图。

`git merge --no-ff dev` 禁用`Fast forward` 模式，合并后的历史有分支。

`git stash` 保存工作区。

`git stash list` 查看`stash` 内容。

`git stash apply` 恢复最近的`stash` 。

`git stash drop` 删除最近的`stach` 。

`git stash pop` 恢复最近的`stash` 同时对其进行删除。

`git stash apply stash@{0}` 恢复指定的`stash` 。

`git branch -d feature-vulcan` 强制删除`feature-vulcan` 分支。

`git remote` 查看远程库信息。

`git remote -v` 显示更详细信息。

`git push origin master/dev` 将`master` 或`dev` 分支推送到远程分支上。

### 标签管理

`git tag <name>` 添加标签。

`git tag <name> <commit id>` 对历史提交添加标签。

`git tag` 查看标签。

`git show <tagname>` 查看标签信息。

`git tag -d v0.1` 删除本地标签。

`git push origin <tagname>` 推送本地标签到远程。

`git push origin --tags` 推送全部未推送到远程的本地标签。

`git git push origin :refs/tags/<name>` 删除远程标签。

### 自定义 Git

`git config --global alias.<abrr> command` 缩写，`--global` 参数是全局参数。 