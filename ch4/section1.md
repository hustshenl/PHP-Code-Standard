# SQL注入

###  定义
代码注入技术，利用一个安全漏洞，在应用程序的数据库层发生。该漏洞是存在的，当用户输入或者不正确的字符串文字转义字符中嵌入SQL语句或用户输入不强类型，从而意外地执行过滤。

### 预防建议

1. 禁止使用字符串拼接构造SQL查询语句
2. 对查询参数的数据类型进行验证，对字符型查询参数过滤特殊字符
3. 使用预备义语句和参数化查询。对于带有任何参数的sql语句都会被发送到数据库服务器，并被解析！对于攻击者想要恶意注入sql是不可能的！

+ 使用PDO(PHP Data Objects )
```php
    $stmt = $pdo->prepare('SELECT * FROM employees WHERE name = :name');
    $stmt->execute(array(':name' => $name));
    foreach ($stmt as $row) {
        // do something with $row
    }
```
+ 使用mysqli
```php
    $stmt = $dbConnection->prepare('SELECT * FROM employees WHERE name = ?');
    $stmt->bind_param('s', $name);
    $stmt->execute();
    $result = $stmt->get_result();
    while ($row = $result->fetch_assoc()) {
        // do something with $row
    }
  ```

### 案例
参见： [http://0day5.com/archives/1834/](http://0day5.com/archives/1834/)

> NOTE: ThinkPHP中Model使用字符串作为查询条件仅对字符串转义后拼接SQL语句，安全性较差；使用数组和对象方式查询则使用预备义语句和参数化查询，安全性较高