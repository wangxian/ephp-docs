# 目录结构

```bash
.
├── Dockerfile
├── LICENSE
├── README.md
├── VERSION
├── app 
│   ├── Controllers
│   │   ├── ApiController.php
│   │   ├── IndexController.php
│   │   └── RootController.php
│   ├── Models
│   │   └── TestModel.php
│   └── Services
│       └── DemoService.php
├── bin
│   ├── cli
│   ├── webdev
│   └── webprod
├── bootstrap
│   └── bootstrap.php
├── bower.json
├── cache
├── composer.json
├── composer.lock
├── conf
│   ├── main.local.php
│   └── routes.php
├── docker
│   ├── nginx.conf
│   ├── php-fpm.conf
│   └── startup.sh
├── logs
├── package.json
├── public
│   └── index.php
├── tests
│   ├── p4.php
│   ├── p7.php
│   ├── p8.php
│   └── t5.tpl
├── vendor
│   ├── autoload.php
│   ├── composer
│   └── wangxian
│       └── ephp
└── views
    └── index
        └── index.tpl
```

## 目录说明

* bin为提供的一些可执行程序，启动内置Server容器
* app为应用程序目录
* public为项目的根目录，如果运行与nginx或apache，请把root设置到public目录
* docker目录，提供docker运行的基本配置文件，可根据情况进行修改
* vendor为第三方依赖目录，包括ephp框架
* tests为测试目录，及测试脚本



