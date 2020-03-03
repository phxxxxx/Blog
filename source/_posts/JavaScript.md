---
title: JavaScript
date: 2020-02-27 21:02:48
tags:
---

# JavaScript基本对象

## Function对象

### 创建

1. `var fun = new Function(形式参数列表，方法体)` 基本不用。
2. 通过`function` 定义方法。形式类型不用写。

```javascript
function fun2(a,b){
	alter(a + b);
}

fun2(3,3);
```

3. var 方法名 = function(){

   }

```
var fun3 = funtion(a,b){
	alter(a-b);
}
```

### 属性

1. length：代表形参的个数。

### 特点

1. 方法的定义是，形参得类型不用写，返回值类型也不写。
2. 方法是一个对象，如果定义了名称相同的方法，会覆盖。
3. 在JS中方法的调用，至于方法的名称有关，和参数列表无关。
4. 在方法声明中有一个隐藏的内置对象，arguments，封装所有的实际参数。

### 调用

1. 方法名称（实际参数列表）；

------

## Array数组对象

### 创建

1. `var array1 = new Array(元素列表)`
2. `var array1 = new Array(length)`
3. `var array3 = [元素列表]`

### 方法

1. `join`（参数）：讲数组中的元素按照指定的分隔符拼接为字符串。
2. `push`：向数组的末尾添加一个或者多个元素，并返回新的长度。

### 属性

1. `length`：数组的长度。

### 特点

1.  `JS`中，数组元素类型是可变的。
2. `JS`中，数组长度是可变的，越界默认为`undefine`。

----

## Date数组对象

### 创建

1. `var date1 = new Date()`

### 方法

1. `tolocaleString`（）：返回当前date对象对应的时间本地字符串格式。
2. `getTime`：获取毫秒值，返回当前对象的时间到1970年1月1日零点的毫秒差值。

----

## Math数学对象

### 创建

* `Math`对象不用创建，之间`Math.function`就可。

### 方法

1. `random()`：返回零到一之间的随机数字，包含零不包含一。
2. `cell()`：对数据向上取整。
3. `floor()`：对数据向上取整。
4. `round()`：返回四舍五入的 值。

---

## Global正则表达式对象

### 正则表达式

* 定义字符串的组成规则。

### 定义

* 单个字符[]。
  *  [a]  [ab] [a-zA-Z0-9]
  * 特殊符号代表特殊含义的单个字符。
    * \d：单个数字字符[0-9]。
    * \w：单个单词字符[a-zA-Z0-9]。
* 量词符号：
  * ?：表示出现零次或者一次。
  * *：表示出现零次或多次。
  * +：出现一次或多次。
  * {m,n}:表示m <= 数量 <= n
    * {,n}: 最多n次。
    * {m，}：最少m次。
* 开始结束符号：
  * `^`：表示开始。
  * `$`：表示结束。

1. `random()`：返回零到一之间的随机数字，包含零不包含一。
2. `cell()`：对数据向上取整。
3. `floor()`：对数据向上取整。
4. `round()`：返回四舍五入的 值。

### 创建

* `var reg = new RegExp("\w{6,14}")`。
* `var reg = /正则表达式/`。

### 方法

1. `test()`：检测是否符合正则表达式。

```javascript
var reg = /^\w{6,13}$/;;
var username = "zhangnijia";

//进行验证
var flag = reg.test(username);
alter(flag)
```

----

## Global数组对象



### 特点

1. 不需要创建，全局直接调用。

### 方法

1. `encodeURI()`：url编码。
2. `decodeURI()`：url解码。
3. `encodeURIComponent()`：url编码，编码的字符更多。
4. `decodeURIComponent()`：url解码。
5. `parseInt()`：讲输入的字符串转成数字（逐一检测，不为数字的不管）。
6. `isNaN`：NaN连自己都不认识，所以需要判断是不是自己。
7. `eval`：讲JavaScript字符串转成脚本执行。

---