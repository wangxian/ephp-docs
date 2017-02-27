# 控制器

正常情况下，控制器需要继承默认控制控制器，以获取一些特殊的功能（ps：如果系统运行在Swoole模式下，一定要继承根Controller，如果在php-fpm下则不强制）

```php
<?php
namespace App\Controllers;

class RootController extends \ePHP\Core\Controller
{    
    public function __construct()
    {
        // @todo ....
    }
}

```



