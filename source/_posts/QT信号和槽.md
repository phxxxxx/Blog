---
title: '***QT信号和槽'
date: 2020-06-11 18:37:45
tags: QT
---

### 信号和槽/自定义信号监听

`widget.cpp`内容

```c++
#include "widget.h"
#include "ui_widget.h"
#include "teacher.h"
#include "student.h"

Widget::Widget(QWidget *parent) :
    QWidget(parent),
    ui(new Ui::Widget)
{
    ui->setupUi(this);

    ui->pushButton->resize(100,50);

    //信号和槽
    //connect(信号发送者，发送的信号|函数的地址，信号的接收者，处理的槽函数）
    //实现点击按钮，接着窗口关闭。
    connect(ui->pushButton,&QPushButton::clicked,this,&Widget::close);
    //注意第四个参数，close不是close()取地址

    //自定义信号和槽

    this->zt = new Teacher(this);
    this->st = new Student(this);

   // connect(zt,&Teacher::hungry,this,&Student::treat);
    connect(zt,&Teacher::hungry,st,&Student::treat);

    connect(ui->pushButton_2,&QPushButton::clicked,this,[=](){
       this->classover();
    });//点击按钮2，调用signal，自定义监听
}

void Widget::classover()
{
   //调用后触发老师饿了发送 signal ->hungry
    emit this->zt->hungry();
}
Widget::~Widget()
{
    delete ui;
}
/*********************************************************************
 *			widget.h 
 *********************************************************************/
#ifndef WIDGET_H
#define WIDGET_H

#include <QWidget>
#include "teacher.h"
#include "student.h"

namespace Ui {
class Widget;
}

class Widget : public QWidget
{
    Q_OBJECT

public:
    explicit Widget(QWidget *parent = nullptr);
    ~Widget();

private:
    Ui::Widget *ui;
    Teacher * zt;
    Student * st;

    void classover();
};

#endif // WIDGET_H

/*********************************************************************
 *			teacher.h 
 *********************************************************************/
#ifndef TEACHER_H
#define TEACHER_H

#include <QObject>

class Teacher : public QObject
{
    Q_OBJECT
public:
    explicit Teacher(QObject *parent = nullptr);

signals:
    //自定义信号，写到signals下面
    //返回值为void，只需要声明，不需要实现
    //可以有参数，可以重载
    void hungry();

public slots:
};

#endif // TEACHER_H
/*********************************************************************
 *			student.h 
 *********************************************************************/
#ifndef STUDENT_H
#define STUDENT_H

#include <QObject>

class Student : public QObject
{
    Q_OBJECT
public:
    explicit Student(QObject *parent = nullptr);

signals:

public slots:
    //返回值为void
    //需要生命，需要实现
    //可以有参数，可以重载
    void treat();

};

#endif // STUDENT_H


```

