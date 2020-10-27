---
title: 解决ssh免密登陆失效问题
date: 2020-09-30 23:28:35
tags: Linux
---

# 解决ssh免密登陆失效问题

#### 1、权限问题

`.ssh`目录，以及`/home/`当前用户 需要700权限，参考以下操作调整

`sudo chmod 700 ~/.ssh`

`sudo chmod 700 /home/`当前用户

`.ssh`目录下的`authorized_keys`文件需要600或644权限，参考以下操作调整

`sudo chmod 600 ~/.ssh/authorized_keys`

#### 2、StrictModes问题

* 编辑

`sudo vi /etc/ssh/sshd_configL`

* 找到

`  #StrictModes yes `

* 改成

`StrictModes no`