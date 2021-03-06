# git

## checkout 远端分支
```
git fetch
git checkout origin/remoteName -b localName
```

## 修改 commit
```
# 对上一次的提交做修改
git commit --amend

# 如果上一次的提交已经push了，那么需要加f参数覆盖服务端，不过不建议
push -f
```

## 暂存
```
git stash [save 注释]

# 恢复保存的工作进度，并将恢复的工作进度从存储的工作进度列表中清除
git stash pop [--index] [\<stash>]

# 恢复保存的工作进度，不删除恢复的进度
git stash apply [--index] [\<stash>]

# 查看 stash 列表
git stash list

# 删除所有存储的进度
git stash clear 
```

## 少用 pull 多用 fetch && merge
```
git fetch

git checkout master && git merge origin/master

# 只是想看看本地分支和远程分支的差异
git diff master origin/master

```

## 撤销 （via: 爱得）
```
# 一、撤销某次不想要的提交
# 删除最近一次提交
git reset --hard HEAD~1 // 取消上一次 commit
git push --force // 同步 

# 通过commit_id来撤消，commit_id之后的提交都会丢失，请小心操作！
git log // 查看commit_id
git reset --hard <commit_id> // 将commit重置到commit_id之前的提交
git push orign HEAD --force // 同步

# 二、简单粗暴、直接
git checkout --orphan latest_branch // 建新分支
git add -A // 添加所有文件
git commit -m "commit message" // 提交更改
git branch -D master // 删除分支
git branch -m master // 将当前分支重命名
git push -f origin master // 强更新
```

## 查看某个文件的提交记录

```
git log -p -<:number> filename
```

## [git flow](https://www.git-tower.com/learn/git/ebook/cn/command-line/advanced-topics/git-flow)

坑：feature finish 时合并到 develop 测试，新功能也是从 develop 切出来，新功能开发完成需要上线时，如果之前的功能未上线，就会有问题。

```
git flow init

# 功能开发
git flow feature start xxx
git flow feature finish xxx

git flow feature help

# 管理 releases
git flow release start 1.0.0
git flow release finish 1.0.0

# 处理 hotfix
git flow hotfix start xxx
git flow hotfix finish xxx
```

## github 更新 fork 项目 (via: [HyG cs](https://www.zhihu.com/question/28676261/answer/44606041))
```shell
# 给fork配置远程库
git remote -v
git remote add upstream https://github.com/ORIGINAL_OWNER/ORIGINAL_REPOSITORY.git

# 同步fork
# 从上游仓库 fetch 分支和提交点，提交给本地 master，并会被存储在一个本地分支 upstream/master
git fetch upstream
# 把 upstream/master 分支合并到本地 master 上
git merge upstream/master
```

## plugin

- [git-extras](https://github.com/tj/git-extras/blob/master/Commands.md)

## config
```
[user]
	name = user
	email = email
[alias]
	ci = commit -a -v
	cm = commit -a -m
	co = checkout
	st = status
	br = branch
	throw = reset --hard HEAD
	throwh = reset --hard HEAD^
	l = log --oneline --decorate -12 --color
	ll = log --oneline --decorate --color
	lc = log --graph --color
	rb = rebase
	dci = dcommit
	sbi = submodule init
	sbu = submodule update
	sbp = submodule foreach git pull
	sbc = submodule foreach git co master
[color]
	ui = true
[push]
	default = current
[core]
	editor = vim
	excludesfile = /Users/x/.gitignore
	ignorecase = false
[pager]
	diff = diff-so-fancy | less --tabs=1,5 -RFX
	show = diff-so-fancy | less --tabs=1,5 -RFX
```
