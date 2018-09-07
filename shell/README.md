# shell snippet

1. 查看进程

    ```
    ps aux | grep php
    ```

2. kill Processes

    ```shell
    # port
    lsof -i:8000
    
    # To kill all PHP Processes
    kill $(ps aux | grep '[p]hp' | awk '{print $2}')

    # To kill all Nginx Processes
    kill $(ps aux | grep '[n]ginx' | awk '{print $2}')

    # To kill all MySQL Processes
    kill $(ps aux | grep '[m]ysql' | awk '{print $2}')
    ```
