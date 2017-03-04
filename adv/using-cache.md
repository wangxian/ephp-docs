# 使用缓存

父控制器继承 `\ePHP\Core\Controller` 后，可以使用 `$this->cache` 获取Cache实例

Cache实例的方法

* $this-&gt;cache-&gt;get\(string $key\)
* $this-&gt;cache-&gt;set\(string $key, mixed $value, int $expires\)
* $this-&gt;cache-&gt;delete\(string $key\)
* $this-&gt;cache-&gt;flush\(\)



可在主配置文件中设置 `cache_driver`

```php
    // 设置缓存驱动方式
    // 可选：file, memcached, redis
    'cache_driver'  => 'file',
```



