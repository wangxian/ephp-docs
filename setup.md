# 框架安装

快速安装ePHP运行需要的环境

## 依赖

1. PHP 5.5.9 及以上版本（建议7.0+）
2. Composer 1.3.0 及以上版本



> 补充**说明：**
> * 开发时不需要安装 nginx 或 apache
> * 根据您的需要安装 PHP 常用扩展，如：curl, gd, mcrypt, mysqli, redis等
> * 如果您已安装了docker，可以拉取代码后，直接 \`docker build -t myapp . && docker run\`



## 安装

```bash
composer create-project wangxian/ephp-installer=dev-master myapp --prefer-dist
```

## 运行

```bash
# cd myapp/

// 运行
# bin/webdev
```

## 可能遇到的问题

### Windows环境下没有bash如何运行框架？

有两种方法可以解决windows下bash问题

第一种：安装git for windows，安装完后会自带git bash, 这样会虚拟出一个linux bash环境

第二种：安装cygwin

### 无法运行webdev

可能的原因，PHP版本过低，或者新安装的PHP不在系统环境变量里，请把安装的PHP的bin目录，加入到系统环境变量里。

