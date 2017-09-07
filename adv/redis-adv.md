# 关于phpredis 或 predis的使用

phpredis是一个C的扩展，性能比predis性能高，缺点是需要编译安装。

predis是一个PHP写的库，性能略低一点，优点是可以方便的使用composer安装，而且功能更全面，支持[redis-sentinel](http://redis.io/topics/sentinel)

最新的ephp在配置中可以方便的切换cache的驱动方式，配置 cache\_driver 为 redis, 或 predis, 配置为redis时使用C扩展，否则使用PHP库。

使用C库，需要安装 [https://github.com/phpredis/phpredis](https://github.com/phpredis/phpredis) 扩展

使用phpredis, 需要使用composer安装predis，在composer.json中添加

```json
"require": {
     "wangxian/ephp": "dev-master",
     "predis/predis": "^1.1"
     ...
}
```

然后使用composer update -vvv 更新依赖即可。

ps：

phpredis, predis 使用方法基本兼容。

**如果要使用redis高级方式的其他类型，可以直接获取redis handle, 直接操作redis**

```php
// 在控制器中
$redis = $this->cache->handle->connection;
dump( $redis->keys('*) );
```



