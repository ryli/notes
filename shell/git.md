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
