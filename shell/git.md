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
