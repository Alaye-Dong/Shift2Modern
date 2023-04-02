---
title: 基础操作
description: Git 基础操作
navigation: false
---

# *Git* 基本操作

::alert{type="info"}
此篇只介绍单人本地进行基础的版本控制，多人协作，多分支等操作指南仍在制作中。
::

## 初始化 `git init`

初始化新仓库：

:terminal{content="git init [repository name]"}

此命令会在当前目录下创建一个名为 `[repository name]` 的文件夹，并在其中创建一个 `.git` 文件夹，用于存放 *Git* 的版本控制数据。

输入 `cd [repository name]` 进入新建的文件夹。


## 添加文件 `git add`

添加文件到暂存区：

:terminal{content="git add [file name]"}

此命令会将当前目录下的 `[file name]` 文件添加到 *Git* 的暂存区。

::alert{type="info"}
也可以使用 `git add .` 将当前目录下的所有文件添加到暂存区。
::


## 删除文件 `git rm`

删除文件：

:terminal{content="git rm [file name]"}

此命令会将当前目录下的 `[file name]` 文件从 *Git* 的暂存区中删除。

::alert{type="info"}
-  `git rm -f [file name]` 可以强制删除文件。
-  `git rm -r [directory name]` 可以删除目录及其子目录下的所有文件。
::


## 撤销修改 `git checkout`

撤销修改：

:terminal{content="git checkout -- [file name]"}

此命令会将当前 *Git* 仓库中的 `[file name]` 文件恢复到上一次提交的状态。

::alert{type="warning"}
此命令会将当前 *Git* 仓库中的 `[file name]` 文件恢复到上一次提交的状态，且无法恢复。
::


## 提交文件 `git commit`

提交文件到本地仓库：

:terminal{content="git commit -m [commit message]"}

此命令会将暂存区中的文件提交到本地仓库，并附带一条提交信息 `[commit message]` 。

::alert{type="info"}
提交信息应该使用 `"` 引出并简洁明了，描述本次提交的内容。
::


## 查看状态 `git status`

查看当前 *Git* 状态：

:terminal{content="git status"}

此命令会显示当前 *Git* 的状态，包括：

- 当前分支
- 本地仓库与暂存区的差异
- 本地仓库与工作区的差异

## 查看提交历史 `git log`

查看提交历史：

:terminal{content="git log"}

此命令会显示当前 *Git* 仓库的提交历史，包括：

- 提交者
- 提交时间
- 提交信息

在提交历史中按下 `q` 键时，即可退出 *Git* 历史查看模式。


## 返回上一版本 `git reset`

返回上一版本：

:terminal{content="git reset --hard HEAD^"}

此命令会将当前 *Git* 仓库的版本回退到上一版本。

::alert{type="info"}
`HEAD^` 表示上一个版本，`HEAD^^` 表示上上一个版本，以此类推。
::

::alert{type="warning"}
此命令模式为 `hard` 时会将当前 *Git* 仓库的所有修改都清空。
::


## 返回指定版本 `git reset`

返回指定版本：

:terminal{content="git reset --hard [commit id]"}

此命令会将当前 *Git* 仓库的版本回退到指定版本。

::alert{type="info"}
`[commit id]` 为提交历史中的提交 ID。
::
