---
title: HTML基本标签
date: 2020-02-23 21:28:05
tags: HTML

---

## HTML基本标签

*<u>标签的各种属性在HTML5中大部分废弃，了解就可，样式控制和交互CSS，JS来做</u>*

-----

 1. 文件标签： 构成html最基本的标签

    * html : html的根标签

    * head ：头标签，用于指定html文档的属性，引入外部资源。

    * title ：标题标签。

    * body ：题标签。

      ---------------

    2. 文本标签：和文本有关的标签

    * `<!-- -->`： 注释的格式

    * `<br>` ：换行标签，html不可以自动换行

    * `<h1>到<h6>`:  标题标签，字体加粗，自动换行，数字越大字体越小。

    * `<p></p>`：段落标签，可以自动换行。

    * `<hr color = "red" width = "300" size = "20" align = "left"/>`：闭合标签，显示一条水平线。有属性但一般用css来控制。此处仅仅举例子。 **HTML5废弃属性**

    * `<b></b>`：用来字体加粗。

    * `<i></i>`：字体斜体。

    * `<center></center>`：文本居中。

    * `<font></font>`：**拥有  color size face  三个属性 **字体标签 HTML5中已经废弃。

      ---------

    ```html
    <!DOCTYPE html>
    <html lang = "en">
        <head>
            <meta charset="UTF-8"
            <title>黑马程序员</title>
        </head>
        <body>
            <h1>
                公司简介
            </h1>
            <hr color = "yellow">
            <font color = "red">i建立和发展了基于不同分子间相互作</font>用的界面分子组装方法，<b><i>粗体加上斜体</i></b>
            <p>
            超分子结构及组装驱动力提供了实验依据。已在国内外学术刊物上发表论文350 余篇。在国际学术会议上做
            特邀报告和大会报告200 余次。
            </p>
            <p>
            建立和发展了基于不同分子间相互作曾获得何梁何利科学与技术进步奖、中
             </p>
             <p>
            中国青年科技奖、中国化学会-巴斯夫青年知识创新奖、国家自然科学二等奖（名列第二）、北京市茅以升
            青年科技高分子学报》主编以及《CCS Chemistry》
            </p>
    <hr color="yellow">
    
    <font color = "gray" size = "2">
        <center>
        吉林省吉林大学科技有限公司<br>
        版权所有Copyright 2000-02-23&copy;
         </center>
    </font>
    
        </body>
    </html>
    ```

    

    3. 图片标签

    * `<img src="image/picturename.jpg" align = "top" alt = "替换文字"/>`：自闭合标签。**alt 图片加载失败后显示alt中的文字** 。

    * `<img src = "./image/1.png">` 代表从当前目录下的image文件夹下载入图片。

    * `<img src = "../image/1.png">` 代表从当前目录下的image文件夹下载入图片。

      ----

    4. 列表标签

    * 有序列表

      * `<ol></ol>` `<li></li>` 

    * 无序列表

      * `<ul type = "disc"></ul>`  `<li></li>` ：菱形点。
      * `<ul type = "circle"></ul>`  `<li></li>`：圆形点。
      * `<ul type = "square"></ul>`  `<li></li>`：方形点。

      -------

```html
<!DOCTYPE html>
<html lang = "en">
    <head>
        <meta charset="UTF-8"
        <title>黑马程序员</title>
    </head>
    <body>
    <ol> <!--顺序排列-->
        <li>早上起床</li>
        <li>接着刷牙</li>
        <li>穿衣服</li>
        <li>上学堂</li>       
    </ol> 
    <ul type = "disc">
        <li>早上起床</li>
        <li>接着刷牙</li>
        <li>穿衣服</li>
        <li>上学堂</li>       
    </ul> 
    <ul type = "circle">
        <li>早上起床</li>
        <li>接着刷牙</li>
        <li>穿衣服</li>
        <li>上学堂</li>       
    </ul> 
    <ul type = "square">
        <li>早上起床</li>
        <li>接着刷牙</li>
        <li>穿衣服</li>
        <li>上学堂</li>       
    </ul> 
    </body>
</html>
```

---------

5. 链接标签

   * `<a herf = "www.google.com">click here</a>`点击 <u> click here </u>跳转到 "www.google.com"
   * `<a herf = "www.google.com" target = "_blank">click here</a>`点击 <u>click here </u>跳转到 "www.google.com"
   * href = "./当前目录下的文件"，也可以这样使用。
   * `<a href = "url"><img src = "image/1.png"></a>`：点击图片跳转到相应的url。

   ---

6. 块标签

   * `<span></span>`：文本信息在一行展示，行内标签，块级标签，没有任何样式，方便JS操作。
   * `<div></div>`：每一个div占满一行，块级标签。

   -------

7. 语义化标签

   * HTML5中为了提高可读性，提供的一些标签。
   * `<header></header>`
   * `<footer></footer>` 

8. 表格标签

   * `<table border = ""></table>`：定义整个最大的外边框表格。 border = ""，没有边框。
     * border ="" 无边框。
     * width：表格宽度。
     * cellpadding：内容和单元格之间的距离。
     * cellspacing：单元格之间的距离，如果为0，则单元格的线会合成一条。
     * bgcolor：背景色。
     * align：对齐方式。
   * `<tr></tr>`：表格的一行 。
     * bgcolor：背景色。
     * align：对齐方式 
   * `<th></th>`：表头中的一列。
     * rowspan：合并行。
     * colspan：合并列。
   * `<td></td>`：表头中的一列(非第一行的列)。
   * `<caption>学生信息表</caption>`：用来做表格的标题。
   * `<thead></thead>`
   * `<tbody></tbody>`
   * `<tfoot></tfoot>`：以上三个作用均为增强代码可读性，表格结构清晰。

9. 表单标签

   * 表单：用于采集用户输入的数据，传给后台服务器。

   * `<form></form>`：框柱`<input>` 标签，定义了用户数据的采集范围。只有包住的数据才会提交。

     * action = “url”  **将数据提交到 url 指定位置**。
     * method = " get/post"  **指定提交方式**。
     * **get 提交方法 请求参数会在地址栏显示，请求参数有限制，不安全**。
     * **post 请求参数不会再地址栏显示，封装在请求体中，参数大小没限制，较安全**。

   * `<input></input>`：用户输入数据的框框。

     * `<input type = "submit" value = "登陆" >`：默认的提交按钮。

     * `<input type = "button" value = "没反应的按钮" >`：点击没反应，用于后期JS。

     * `<input type = "text" name = "username" placeholder = "请输入用户名">`：文本输入框。

       <b><font color = "red">placeholder = "请输入用户名"</font></b>   输入时默认出现的提示信息，输入时自动清空提示信息。

     * `<input type = "password" name = "password">`：密码是小圆圈看不见的输入。

     * `<input type = "radio" name = "gender" value = "male" checked = "checked">`

     * `<input type = "radio" name = "gender" value = "female">`

       **两个想实现单选，name属性必须一致，value赋值传给服务器,checked代表默认选中** 

     * `<input type = "checkbox" name = "hobby" value = "shopping">`

       `<input type = "checkbox" name = "hobby" value = "learn">`

       **注意多选也必须用 value** ，name = "username" **只有name被加上数据才会被拼接提交。**

     * `<input type = "file" name = "选择文件">`： 选择文件按钮。

     * `<input type = "hidden" name = "id">`： 隐藏域，用于提交一些信息。

     * `<input type = "image"  src= "url">`： 用图片做背景自动提交。

     * `<input type = "date" name = "birthday">`： 用于帮助用户选择自己生日的小组件。

     * `<input type = "datetime-local" name = "birthday">`： 用于帮助用户选择自己生日的小组件。更加具体到时分。 

     * `<label for = "@@@"></label>` 与 input 的 id 属性对应，点击label区域，则输入框获得光标。

   * ```html
     <select name = "province">
         <option value="">--请选择--</option>
         <option value="1">北京</option>
         <option value="2">吉林</option>
         <option value="3" selected>深圳</option>
     </select>
     ```

   * `<textare cols ="制定的列" rows ="制定的行" name = "descr" ></textare>`

​        





