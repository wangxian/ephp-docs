# Session使用

方法一

```php
// 控制器已继承\ePHP\Core\Controller
$this->session->set('user', ['info' => ['id'=>820, 'name'=>'wx']]);

// 获取cookie， 支持直接获取多维数据的session
$this->session->get('user.info.name');

// 删除session，只支持一维的方式删除
$this->session->delete('user');

// 删除所有
$this->session->deleteAll();

// 说明：
// 更改session name, 默认pppid
// 在配置文件`main.php`中，设置 
// 'session_name' => 'pppid',
```

方法二

```php
// 控制器没继承\ePHP\Core\Controller
$cookie = new \ePHP\Http\Session();
$cookie->set($name, $value);

// ... 同上
```



