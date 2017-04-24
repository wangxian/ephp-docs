# Httpclient

```php
// 发送GET请求
$this->httpclient->get('http://test.com/index/echo')->body;

// 发送POST请求
// timeout 超时时间，单位秒
$this->httpclient->post('http://test.com/index/echo',
    ['id'=>12],
    ['headers'=>["TEST: act.qq.com"], 'timeout'=>1]
);

// 返回的数据结构
- content_type 文档类型
- status_code http状态码
- headers 响应header头
- body 内容体

// 支持发送的请求
- get($url, $params = array(), $options = array())
- post($url, $params = array(), $options = array())
- put($url, $params = array(), $options = array())
- patch($url, $params = array(), $options = array())
- delete($url, $params = array(), $options = array())

// 上传文件
$this->httpclient->post('http://apib2.wboll.com/index/echo',
    ['id'=> 'postdata'],
    [
        'files'=> [
            'hosts' => '/etc/hosts',
            'pic'   => '/tmp/abc.png'
        ]
    ]
);
```



