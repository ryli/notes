## base operation

### 忽略插入
```
INSERT IGNORE INTO `table_name` (`phone`, `user_id`) VALUES ('13322221111', '9999');
```

### 更新或插入
```
INSERT INTO t1 (a,b,c) VALUES (1,2,3) ON DUPLICATE KEY UPDATE c=1;
```
