# 模型

模型使用方法

```php
$this->model->table("mnh_user_address")
    ->where(['openid' => $this->openid])
    ->orderBy("id desc")
    ->findAll();
    

$date1 = '2017-04-25 16:00:25';
$date2 = '2017-05-25 16:00:25';

// 使用 ? 匹配替换变量
$this->model->table("mnh_orders")->where("deleted_at is null and created_at > ? and created_at <= ?", [$date1, $date2])
     ->findAll();
     
// 最后执行的SQL     
echo $this->model->sql;     
```



**模型方法**

* table\($table\_name\)
* dbconfig\($db\_config\_name\)
* cache\($expire\)
* select\($field\)
* field\($field\)
* limit\($offset, $limit = 0\)
* set\($data, $replacement = array\(\)\)
* data\($data, $replacement = array\(\)\)
* where\($where, $replacement = array\(\)\)
* leftjoin\($join\_string\)
* rightjoin\($join\_string\)
* orderby\(string $orderby\)
* groupby\(string $groupby\)
* having\(string $having\)
* int affected\_rows\(\)
* int insert\_id\(\)
* query\($sql, $replacement = array\(\)\)
* mixed find\(\)
* mixed findAll\(\)
* mixed findObj\(\)
* mixed findObjs\(\)
* array findPage\(\)  // 返回：array\('data'=&gt;\[\], 'data\_count'=&gt;0\)
* int count\(\)
* bool delete\(bool $f\)
* int update\(bool $f\)
* int insert\(\)
* int insert\_update\($update\_string = ''\)
* int insert\_replace\(\)
* trans\_start\(\)
* trans\_commit\(\)
* trans\_rollback\(\)
* escape\_string\($str\)





