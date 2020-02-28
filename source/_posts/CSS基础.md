---
title: CSS基础
date: 2020-02-25 22:14:20
tags: CSS
---

## CSS：页面美化和布局控制

### 概念：层叠样式表

* 层叠：多个样式可以作用在同一个html元素。

--------

### 好处

* 功能强大。
* 将内容展示和样式控制分离。
  * 降低耦合度，解耦。
  * 分工合作更简单，提高开发效率。

-------

### CSS 和HTML的结合

* 内联样式
  * 在标签内使用style属性指定css代码。
  * 例子 `<div style = "color: red;>like coding</div>"`
* 内部样式
  * 位于head标签内，定义style标签，style标签的标签体内容就是css代码。

```html
<style>
    <div>{
        color: red;
    }
</style>

<div>like coding</div>
```

* <font color = "red">外部样式</font>
  * 定义css资源文件
  * 在head标签内，定义link标签，引入外部的资源文件。

```html
<!-- 首先路径下有a.css文件 -->

div{
	color：red;
}

<link rel = "stylesheet" href = "css/a.css"> 

<div>
    like coding
</div>

<div>
    like coding
</div>
```

   *  三种方式区别，css作用范围越来越大。
      * 一方式不常用，一般常用二和三。
      * 第三种格式不常用的写法有`<style>@import "css/a.css"<style>`。

----

### 	css基本语法

* 格式

```css
选择器{
    属性名1：属性值1;
    属性名1：属性值1;
    ...
}
```

* 筛选具有相似特征的元素。
* 每一对属性都需要使用`;`隔开。最后一对可以不加。 

-------

### 选择器：筛选具有相似特征的元素

* 基础选择器
  * id选择器：选择具体的id属性值的元素，建议一个HTML页面id值唯一。
    * 语法：#id属性值{ }
  * 元素选择器：选择具有相同标签的元素。
    * 语法：标签名称{ }
    * 注意：id选择器优先级高于元素选择器。
  * 类选择器：选择具有相同class属性值的元素。
    * 语法：`.class`属性值{ }
    * 注意：类选择器优先级高于元素选择器。

```html
<style>
    #div1{
       color: red;
    }
    
    div{
       color: green;
    }
    
    .class{
       color: blue;
    }
</style>
```

* 扩展选择器：
  * 选择所有的元素  `*{}`
* 并集选择器：
  * 选择器1，选择器2{ }
* 子选择器：筛选选择器1元素下的选择器二元素。
  * 选择器1 选择器2 { }
* 父选择器：筛选选择器2的父元素选择器1。
  * 选择器1 > 选择器2 { }
* 属性选择器：选择元素名称，属性名等于属性值的元素。
  * 元素名称[属性名= "属性值"]{ }
* 伪类选择器：选择一些元素具有的状态。
  * 元素：状态{ }
  * 如：`<a>`
    * `link`：初始化的状态。
    * `visited` ：被访问过的状态。
    * `active`：正在访问的状态。
    * `hover`：鼠标悬浮状态。

```html
<style>
    div p{
        color:red;
    }
    
    div > p {
        color:green;
    }
    
    input [type = "text"]{
        border: 5px solid;
    }
    
    a:link{
        color: red;
    }
    
    a:hover{
        color: green;
    }
    
    a:active{
        color:yellow;
    }
    
    a:visited{
        color: blue;
    }
    
    
</style>

<body>
    <div>
        <p>
            likoding
        </p>
    </div>
    
    <div>
        likding
    </div>
    
    <p>
        likoding
    </p>
    
    <input type = "text">
    
    <a>lung</a>
    
</body>
```

----

### CSS属性

* 字体，文本
  * `font-size `：字体大小。
  * `text-align`：对齐方式。
  * `border`：边框的属性，可以分开设置。
  * `line-height`：行高。
* 尺寸
  * `width`：宽度。
  * `height`：高度
* 背景
  * `background`：背景。
* 边框
  * `border`：设置边框，符合属性。
* 盒子模型：页面布局的控制。 
  * `margin`：外边距。
  * `padding`：内边距。
    * 默认内边距会影响整个盒子大小。
    * `box-sizing：border-box；` 设置盒子属性，让`width`和`height`就只最终盒子大小。
  * `float`
    * `float：left`
    * `float：right`