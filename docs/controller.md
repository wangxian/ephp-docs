# 控制器

正常情况下，控制器需要继承默认控制控制器，以获取一些特殊的功能（ps：如果系统运行在Swoole模式下，一定要继承根Controller，如果在php-fpm下则不强制）

```php
<?php
namespace App\Controllers;

class RootController extends \ePHP\Core\Controller
{    
    public function __construct()
    {
        // @todo ...
    }
}
```

**控制器对象：**

* $this-&gt;view
* $this-&gt;session
* $this-&gt;cookie // 兼容 swoole
* $this-&gt;server // swoole only
* $this-&gt;httpclient 使用方法参考 常用类库-&gt;Httpclient 类
* $this-&gt;cache

**控制器方法：**

* protected function stopRun\(\) 停止当前request，主要用在swoole模式，替代exit

* protected function isAjax\(\) 判断当前请求是否是ajax请求



