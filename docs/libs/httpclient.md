# Httpclient

```php
// 发送GET请求
$this->httpclient->get('http://test.com/index/echo');

// 发送POST请求
// timeout 超时时间，单位秒
$this->httpclient->post('http://test.com/index/echo',
    ['id'=>12],
    ['headers'=>["TEST: act.qq.com"], 'timeout'=>1]
)->body;

// 上传文件
$this->httpclient->post('http://apib2.wboll.com/index/echo',
    ['id'=> 'postdata'],
    [
        'files'=> [
            'hosts' => '/etc/hosts',
            'pic'   => '/tmp/abc.png'
        ]
    ]
)->body;
```



