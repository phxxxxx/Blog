---
title: gcc编译器的编译命令
date: 2020-03-15 08:43:50
tags: 编译器
---

# GCC编译器的使用

## 前言

​	由于visual studio对于不经常使用的我来说太过于臃肿，于是考虑使用gcc编译器对单个c文件进行编译。方便平时的学习，故在此记录。**使用gcc可以直观的感受到变异的四个步骤，预编译，编译，汇编，连接。**

## 预编译

* 预编译， 讲带#的语句重新展开到制定文件中，比如#define， #include "*.h"

```c
gcc -E main.c -o main.i
```

## 编译

* 将.o文件编译成汇编文件（.s文件）。

```c
gcc -S main.c -o mian.s
```

## 汇编

* 相比-S命令，多了assemble，生成目标文件（.o文件）

```c
gcc -c main.c -o mian.o
```

## 将.c文件直接编译成可执行文件或.o文件

```c
gcc main.c -o main
```

## 其他命令

* `-std`：使用哪个c语言标准编译。

```cpp
// 使用c99编译
gcc -std=c99 
// 使用gnu99(c99的gnu扩展)编译
gcc -std=gnu99
```

* 编译静态库

```swift
gcc -c hello.c -o hello.o
ar -r libhello.a hello.o hello2.o 
//( 静态库名称规则： lib+名字+.a（）, 否则在使用-l链接的时候会找不到）
gcc main.c libhello.a -o main
// 或者：
gcc -L ./ main.c -lhello -o main  //(-L制定库的搜索路径，-l调用链接库)
//.a表示archive归档。ar类似于tar，起打包的作用。                                    
```

* 编译动态库。

```c
gcc -c -fpic hello.c （fpic：采用浮动地址）
gcc -shared hello.o -o hello.so  (.so告诉编译器编译成动态库，省略的话会编译成exe）
合并：gcc -fpic -shared hello.c -o hello.so
```