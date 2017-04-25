# 视图

**渲染视图**

```php
// 说明，render() 可以省略视图名称，默认为当前控制器名称，操作名称.tpl
// 比如控制器=index,操作=index, 默认为 index/index.html
$this->view->render('user/info.html');
```



**传值**

```php
// 推荐，使用对象方式， 在view中使用<p><?php echo $this->name;?></p>
$this->view->name  = 'ePHP';

或

// 推荐，使用对象方式， 在view中使用<p><?php echo $name;?></p>
$this->view->assign('name', 'ePHP');
```



**控制器方法**

* assign\(string $key, mixed $value\)

* render\($file = '', $expire = -1, $layout\_block = false\)

* is\_cached\($file = ''\)

* layout\($file = '', $expire = -1\)

* \_extends\($file\)

* \_block\($block\_name\)

* \_endblock\(\)

* \_include\($file, $\_\_vars = null, $layout\_block = false, $return = false\)



