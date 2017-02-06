# 使用后台任务

服务启动时，监听task事件

```php
// Create production server
$http = \ePHP\Core\Server::init()->createServer($config);

// Register a task Listener for handle Async Task
// Backend Task
$http->server->on('task', function (\swoole_server $serv, $task_id, $from_id, $data)
{
    var_dump("task-data=", $data);

    // return to the worker
    return $data;
});

$http->start();
```



在控制器，推到异步任务到任务队列，并异步得到结果

```php
\ePHP\Core\Server::init()->server->task(["jobName"="log", "data"="...."], -1, function (\swoole_server $serv, $task_id, $data)
{
    var_dump($data);
});
```



