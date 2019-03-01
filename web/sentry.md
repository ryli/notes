# sentry 基本使用

本文介绍的是 nodejs，其他语言可以参考[官方文档](https://docs.sentry.io/clients/)。

## add new project

1. 在后台点击`创建项目`
2. 选择`框架语言`，可选 node.js, Express, Koa
3. 填写`项目名称`
4. 选择`开发小组`
5. 点击`创建项目`
6. 在配置页面，记录生成的`Sentry DSN`, 例如： `https://f5b6564846344aae86ddd396819666f6@sentry.some-domain.cn/25`

## Installation

```shell
npm install raven --save
// typescript
npm install @types/raven --dev
```

## Configuring

[相关文档](https://docs.sentry.io/clients/node/usage/)

在项目入口文件内加入以下代码：

```js
const Raven = require('raven')
const { isLocal } = require('./config')

// 上面生成的 Sentry DSN
const DSN = 'https://f5b6564846344aae86ddd396819666f6@sentry.some-domain.cn/25'
// 取消命令行提醒
Raven.disableConsoleAlerts()
// 屏蔽本地开发时上传错误
Raven.config(!isLocal && DSN).install()

// 使用示例 1
try {
  doSomething(a[0])
} catch (e) {
  // 上报错误
  Raven.captureException(e)
}

// 使用示例 2，这样也可以上报错误
Raven.context(function() {
  doSomething(a[0])
})

// 使用示例 3, Express
// The error handler must be before any other error middleware
app.use(Raven.errorHandler())

// 使用示例 4, Koa
app.on('error', function (err) {
  Raven.captureException(err)
})

process.on('uncaughtException', err => {
  console.error(err)
  // 上报错误
  Raven.captureException(err)
})

process.on('unhandledRejection', (reason, p) => {
  console.log(`Unhandled Rejection at:`, p, 'reason:', reason)
  // 上报错误
  Raven.captureException(reason)
})
```
