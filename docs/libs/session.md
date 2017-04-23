# Session使用

方法一

```php
// 控制器已继承\ePHP\Core\Controller
$this->session->set($name, $value);

// 获取cookie， 支持直接获取多维数据的session
$this->session->get('user.name');
```



方法二

```php
// 控制器没继承\ePHP\Core\Controller
$cookie = new \ePHP\Http\Session();
$cookie->set($name, $value);
// ... 同上
```



