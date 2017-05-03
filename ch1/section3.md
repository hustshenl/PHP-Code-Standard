# 三、控制结构
1. switch 语句
    + `case`应换行，并与`switch`对齐
    + `case`后不需要换行
    + `break`后应空一行
 
2. 长的if语句应该分多行
+ 运算符放到下一行开头，并四个空格缩进，第一个条件式应与下一行的条件式对齐
```php
    if (   $condition1
    || $condition2
    || $condition3
    ) {
    //code here
    }
```
    
+  当复合的条件式不够清晰时，应该将复合条件式独立出单独到单独的变量中。使得阅读者可以一眼看出条件表达式所要表达的意思
```php
    $is_foo = ($condition1 || $condition2);
    $is_bar = ($condition3 && $condtion4);
    if ($is_foo && $is_bar) {
    // ….
    }
```
这一条同样适用于三目运算符的条件式，当三目运算符的条件式比较复杂且不够清晰是，可以独立到单独的变量中
    