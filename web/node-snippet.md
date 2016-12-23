## yarn
```shell
yarn config get registry
# -> https://registry.yarnpkg.com

yarn config set registry 'https://registry.npm.taobao.org'
# -> success Set "registry" to "https://registry.npm.taobao.org".

```

## nvm
> Manual upgrade

1. change to the $NVM_DIR
2. pull down the latest changes
3. check out the latest version
4. activate the new version

```
(
  cd "$NVM_DIR"
  git fetch origin
  git checkout `git describe --abbrev=0 --tags --match "v[0-9]*" origin`
) && . "$NVM_DIR/nvm.sh"
```
[nvm](https://github.com/creationix/nvm#manual-upgrade)
