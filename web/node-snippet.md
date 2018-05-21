## yarn registry
```shell
yarn config get registry
# -> https://registry.yarnpkg.com

yarn config set registry 'https://registry.npm.taobao.org'
# -> success Set "registry" to "https://registry.npm.taobao.org".
# origin:  https://registry.npmjs.org/
```
### 选择性依赖项解决 
在 package.json 文件里添加 resolutions 字段，用于覆盖版本定义：
```js
{
  "name": "project",
  "version": "1.0.0",
  "dependencies": {
    "left-pad": "1.0.0",
    "c": "file:../c-1",
    "d2": "file:../d2-1"
  },
  "resolutions": {
    "d2/left-pad": "1.1.1",
    "c/**/left-pad": "1.1.2"
  }
}
```

## nvm
> config

```shell
export NVM_NODEJS_ORG_MIRROR=http://npm.taobao.org/mirrors/node
export NVM_IOJS_ORG_MIRROR=http://npm.taobao.org/mirrors/iojs
```

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

## other
> chromedriver, phatomjs, selinjum

```shell
export PHANTOMJS_CDNURL=http://npm.taobao.org/mirrors/phantomjs
export CHROMEDRIVER_CDNURL=http://npm.taobao.org/mirrors/chromedriver
export SELENIUM_CDNURL=http://npm.taobao.org/mirrorss/selenium
```

## debug

```
node --inspect app.js

node --trace-warnings app.js

node --trace-deprecation app.js

node --throw-deprecation app.js
```

