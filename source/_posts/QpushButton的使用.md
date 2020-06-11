---
title: QpushButton的使用
date: 2020-06-11 15:49:21
tags: QT
---

### QpushButton控件的使用

* Qpushbutton控件发现按钮细节不好调，直接谷歌搜一个按钮图片，有海量的按钮直接使用样式表就可。不用傻傻的自己设计

```c++
"border-image:url(:/image/1.PNG)"
```

* qpushbutton控件常用操作

```c++
Widget::Widget(QWidget *parent) :
    QWidget(parent),
    ui(new Ui::Widget)
{
    ui->setupUi(this);

    resize(600,800);  //widget固定大小。

    ui->pushButton->resize(300,100);//按钮设置大小

    ui->pushButton->setText("my_push_button");  //设置按钮文本

    ui->pushButton->setGeometry(150,150,100,150);

    ui->pushButton->setStyleSheet("border-image:url(:/image/1.PNG)");   //使用样式表进行icon自适应大小。

    ui->pushButton->setIcon(QIcon(":/image/1.PNG"));  //设置按钮icon

   // ui->pushButton->setFlat(true);//窗口变得透明

  //  ui->pushButton->setStyleSheet("QPushButton{ color: rgb(245,45,135)}");

    /*不使用ui，手动创建btn*/
    QPushButton * btn = new QPushButton("TEXT",this);



}
```