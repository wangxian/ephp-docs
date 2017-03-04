# 关于连接池

ePHP 已经支持了数据库连接池。  
不过需要Server运行于 `swoole` 容器下， dbdriver 设置为 mysqlco, 并配置 idle\_pool\_size 和 max\_pool\_size

**概念解释：**

* mysqlco 使用基于协程MySQL客户端驱动的方式
* idle\_pool\_size 为默认空闲数据库连接数
* max\_pool\_size 最大连接池大小



启用数据库连接池，需要在主配置main.config.php文件中配置

```php
     // 数据库驱动配置，可选：mysqli, mysql, sqlite3, mysqlco
    'dbdriver'      => 'mysqlco',
    
    // 数据库配置
    'dbconfig'      => [
        // default db
        'default' =>
        [
            'host'      => '127.0.0.1',
            'user'      => 'root',
            'password'  => '111111',
            'dbname'    => 'test',
            'port'      => '3306',
            'tb_prefix' => 't_',
            'charset'   => 'utf8',

            // Max mysql pool size
            // Only support dbdriver mysqlco
            'idle_pool_size' => 5,
            'max_pool_size'  => 10
        ],
```





