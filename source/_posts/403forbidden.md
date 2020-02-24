---
title: 403forbidden
date: 2020-02-23 20:21:28
tags: 网站运维
---

## 403 forbidden Nginx

### 原因一:Nginx没有对应web目录下的用户权限

查看nginx日志，路径为nginx/error.log。打开日志发现报错Permission denied。则相应的权限出问题。nginx没有web目录的操作权限。重新分配权限即可。

-----

### 原因二：网站根目录缺少索引文献

查看网站根目录，发现重新depoly以后，不知为何index.html 位于网站子目录下。复制一份移动到根目录，问题解决。

