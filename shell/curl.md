# CURL

## 查查源码
`curl http://www.xx.com`

## 保存网页
`curl -o [文件名] http://www.xx.com`

## 显示头信息
`curl -i http://www.xx.com`

## 显示全过程
`curl -v http://www.xx.com`

## 发送GET数据
`curl http://www.xx.com?name=xx`

## 发送POST数据
`curl --data "data=xxx" http://www.xx.com`
`curl --data-urlencode "data=xxx" http://www.xx.com`

## 设置UA
`curl --user-agent "Mozilla/5.0 (iPhone; CPU iPhone OS 7_0 like Mac OS X; en-us) AppleWebKit/537.51.1 (KHTML, like Gecko) Version/7.0 Mobile/11A465 Safari/9537.53" http://www.xx.com`

## 设置Cookie
`curl --cookie "name=xxx" http://www.xx.com`

## 设置Header
`curl --header "name: xxx" http://www.xx.com`

## 设置Referer
`curl --referer http://www.from.com http://www.xx.com`

## 设置Header
`curl --header "name: xxx" http://www.xx.com`

## 文件上传
`curl --form upload=@localfilename --form press=OK http://www.xx.com`

## 支持跳转
`curl -L http://www.xx.com`
