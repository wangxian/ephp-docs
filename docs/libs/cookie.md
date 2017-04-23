# Cookie使用

方法一

```php
// 控制器已继承\ePHP\Core\Controller
$this->cookie->set($name, $value, $expire = 604800, $path = '/', $domain = '');
$this->cookie->setSecret($name, $value, $expire = 604800, $path = '/', $domain = '');

$this->cookie->get($name);
$this->cookie->getSecret($name);
```

方法二

```php
// 控制器没继承\ePHP\Core\Controller
$cookie = new \ePHP\Http\Cookie();
$cookie->set($name, $value, $expire = 604800, $path = '/', $domain = '')

// ... 同上
```



