# 视图

## 一、基础使用

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



## 二、高级使用技巧

布局视图

app/Controllers/IndexController.php

```php
$this->view->layout('user/changepwd.html');
```

views/\_layout/default.html

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="keywords" content="">
  <meta name="description" content="">
  <meta name="author" content="" />
  <meta name="robots" content="index,follow" />
  <meta name="copyright" content="copyright 2012 xx.cn" />

  <title><?php $this->_block('title'); ?><?php $this->_endblock(); ?>网站标题</title>
  
  <?php $this->_block('more_head'); ?>
  <?php $this->_endblock(); ?>

  <?php $this->_block('more_style'); ?>
  <?php $this->_endblock(); ?>

</head>
<body>
<div id="wrapper">

<?php $this->_block('header'); ?>
  <?php $this->_include('_include/header'); ?>
<?php $this->_endblock(); ?>

  <div id="content">
  <?php $this->_block('content'); ?>

    <div id="main">
    <?php $this->_block('main'); ?>

      <div id="search">
      <?php $this->_block('search'); ?>
      <?php $this->_endblock(); ?>
      </div><!-- end #search -->

      <div id="items">
      <?php $this->_block('items'); ?>
      <?php $this->_endblock(); ?>
      </div><!-- end #list -->

    <?php $this->_endblock(); ?>
    </div><!-- end #main -->

    <div id="aside">
    <?php $this->_block('aside'); ?>
    <?php $this->_endblock(); ?>
    </div><!-- end #aside -->

  <?php $this->_endblock(); ?>
    <div class="clear"></div>
  </div><!-- end #content -->

<?php $this->_block('footer'); ?>
  <?php $this->_include('_include/footer'); ?>
<?php $this->_endblock(); ?><!-- end #footer -->

</div><!-- end #wrapper -->

<?php $this->_block('overlay'); ?><?php $this->_endblock(); ?><!-- end overlay -->

<script type="text/javascript" src="/js/core/jquery-1.7.2.min.js"></script>
<?php $this->_block('script'); ?><?php $this->_endblock(); ?>

<div style="display: none;">
<script type="text/javascript">
</script>
</div>
<!-- END baidu tongji -->

</body>
</html>

```



views/user/changepwd.html

```html
<?php $this->_extends('_layout/default'); ?>

<?php $this->_block('style');?>
<style type="text/css">
.md p.pwd-t1 { font-size: 30px; font-weight: bold; padding: 0px 0px 18px 0px; }
.md p.pwd-t2 { font-size: 14px; line-height: 32px;}
.md p.pwd-input { font-size: 14px; line-height: 30px; padding: 0px 0px 10px 0px; }
.md p.pwd-btn { padding: 14px 0px 0px 0px;}
.md span.error { color: red; font-size: 12px;}
.md span.tip { color:#B3B3B3; font-size: 12px; }

#register_sucess {margin: 4px 0;}
#register_sucess p{ font-size:16px;font-weight:bold; margin:0px 0px 6px 0px; }

.afnor { color:#000; text-decoration:underline; }
</style>
<?php $this->_endblock();?>

<?php $this->_block('content'); ?>
<div id="main">
    <div class="md">

        <form id="form1" name="form1" action="" method="post">
            <?php if(Session::get("webuser.phone")): ?>
            <p class="pwd-t1">修改密码</p>
            <p class="pwd-t2">手机号：</p>
            <p class="pwd-input">
                <span class="text-span"><?php echo Session::get('webuser.phone');?></span>
            </p>
            <?php endif;?>

            <p class="pwd-t2">当前密码：</p>
            <p class="pwd-input">
                <input type="password" name="curpwd" id="curpwd" class="text" value="<?php echo postv('curpwd');?>" />
                <span class="error"><?php if(isset($errors['curpwd'])):?><?php echo $errors['curpwd'];?><?php endif;?></span>
            </p>
            <p class="pwd-t2">新密码：</p>
            <p class="pwd-input">
                <input type="password" name="newpwd" id="newpwd" class="text" value="<?php echo postv('newpwd');?>" />
                <?php if(!isset($errors['newpwd'])):?>
                    <span class="tip">密码长度6-20位，字母区分大小写</span>
                <?php else:?>
                    <span class="error"><?php echo $errors['newpwd'];?></span>
                <?php endif;?>
            </p>
            <p class="pwd-t2">确认新密码：</p>
            <p class="pwd-input">
                <input type="password" name="newpwd2" id="newpwd2" class="text" value="<?php echo postv('newpwd2');?>" />
                <span class="error"><?php if(isset($errors['newpwd2'])):?><?php echo $errors['newpwd2'];?><?php endif;?></span>
            </p>
            <p class="pwd-btn">
                <span class="bn-flat">
                    <input type="submit" value="提交" onclick="javascript:this.disable=true;this.value='正在提交...';" />
                </span>
            </p>

        </form>
    </div>
</div>
<?php $this->_endblock(); ?>

<?php $this->_block('content'); ?>
<script type="text/javascript">
// todo...
</script>
<?php $this->_endblock(); ?>
```



