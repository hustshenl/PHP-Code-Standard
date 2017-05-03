# 四、函数调用
 
1.  函数在被调用时，函数名与其左花括号之间不能有空格（对于花括号不换行的），函数参数与两个括号之间也不能有空格，但是后一个参数与前一个参数的逗号之间必须有一个空格，参数逗号与左边的参数不能有空格

 ```php
     $var = foo($bar, $baz, $quux);
 ```
 
2.  函数调用的对齐（这一条同样适用于所有的其他表达式）
 当有几行函数赋值的调用，那么被赋值的变量，应以等号对齐(太长的就不需要了，要适可而止，主要是为了清晰好看)
 
```php 
     $short         = foo($bar);
     $long_variable = foo($baz);
     
     $is_shame = ($condition1 || $condition2);           // sd fds f
     $is_girl      = ($condition3 && $condition4);       // dsfdsaf
```
 
3. 当函数参数过多时，应该分行，并对齐，第一个换行的参数应该以四个空格缩进，使阅读清晰
 
 ```php
     $this->someObject->subObject->callThisFunctionWithALongName(
     $parameterOne, $parameterTwo,
     $aVeryLongParameterThree
     );
```
  
 加强版

```php    
     $this->someObject->callThisFunctionWithALongName(
     $parameterOne,
     $parameterTwo,
     $aVeryLongParameterThree,
     $aVeryLong,
     $aVeryLong
     );
     
     $this->sObject->call($parameterOne,
     $parameterTwo,
     $aVeryLongParameterThree,
     $aVeryLong,
     $aVeryLong);
```
  
4. 函数的链式调用过多，应分行，第一个分行的方法应该以四个空格缩进

```php 
     $someObject->someFunction("some", "parameter")
     ->someOtherFunc(23, 42)
     ->andAThirdFunction();
```