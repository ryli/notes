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

## 撤销 （via: 爱得大大）
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
