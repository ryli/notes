# shell snippet

1. 查看进程

    ```
    ps aux | grep php
    ```

2. kill Processes

    ```shell
    # 查看 port
    lsof -i:8000
    netstat -an | grep 8000
    
    # To kill all PHP Processes
    kill $(ps aux | grep '[p]hp' | awk '{print $2}')

    # To kill all Nginx Processes
    kill $(ps aux | grep '[n]ginx' | awk '{print $2}')

    # To kill all MySQL Processes
    kill $(ps aux | grep '[m]ysql' | awk '{print $2}')
    ```

3. find

  ```shell
  # 删除当前目录下所有 node_modules 文件
  find . -name "node_modules" -type d -prune -exec rm -rf '{}' +
  ```
 
 
