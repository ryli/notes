# qconf

## Mac 找不到 libqconf.dylib
>  via: 谦姐

```shell
# 在 shell 配置里添加
export DYLD_LIBRARY_PATH=$DYLD_LIBRARY_PATH:$QCONF_INSTALL/lib

# 因为 DYLD_* 这些环境变量在启动一个受保护的进程时会被净化掉，所以使用 nodemon 的话继续下面的步骤
cd ./node_modules/node-qconf/build/Release/

# 查看
otool -L qconf.node
# qconf.node:
#   libqconf.dylib (compatibility version 0.0.0, current version 0.0.0)
#   ...

# 修改引用路径
install_name_tool -change libqconf.dylib /usr/local/qconf/lib/libqconf.dylib ./qconf.node

# 再次查看
otool -L qconf.node
# qconf.node:
#   /usr/local/qconf/lib/libqconf.dylib (compatibility version 0.0.0, current version 0.0.0)
#   ...
```
