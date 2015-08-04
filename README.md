#git 学习笔记

-----------------------------------------------------
## 创建新仓库
创建新文件夹，打开，然后执行 `git init` 以创建新的 git 仓库。

## 检出仓库
执行如下命令以创建一个本地仓库的克隆版本：

`git clone /path/to/repository`

如果是远端服务器上的仓库，你的命令会是这个样子：

`git clone username@host:/path/to/repository`

## 工作流
本地仓库由 git 维护的三棵“树”组成。

*   第一个是你的 工作目录，它持有实际文件；
*   第二个是 缓存区（Index），它像个缓存区域，临时保存你的改动；
*   最后是 HEAD，指向你最近一次提交后的结果。`

## 添加与提交
计划改动（把它们添加到缓存区），使用如下命令：

`git add <filename>`

使用如下命令以实际提交改动,改动提交到了 HEAD

`git commit -m "代码提交信息"`

执行如下命令以将这些改动提交到远端仓库：

`git push origin master`

注：可以把 master 换成你想要推送的任何分支。

## 分支

创建一个叫做“feature_x”的分支，并切换过去：

`git checkout -b feature_x`

切换回主分支：

`git checkout master`

把新建的分支删掉：

`git branch -d feature_x`

## 更新与合并
要更新本地仓库至最新改动：

`git pull`

要合并其他分支到当前分支：

`git merge <branch>`

注：自动合并并非次次都能成功，并可能导致 冲突（conflicts）

在合并改动之前，也可以使用如下命令查看：

`git diff <source_branch> <target_branch>`

## 替换本地改动
使用 HEAD 中的最新内容替换掉工作目录中的文件

`git checkout -- <filename>`

假如你想要丢弃你所有的本地改动与提交，可以到服务器上获取最新的版本并将你本地主分支指向到它：

`git fetch origin`

`git reset --hard origin/master`
