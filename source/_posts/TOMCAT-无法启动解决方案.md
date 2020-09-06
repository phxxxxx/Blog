---
title: TOMCAT 无法启动解决方案
date: 2020-09-06 10:25:02
tags: WEB开发
---

#### 端口冲突导致tomcat启动失败

首次使用tomcat，运行时出现失败，浏览器显示

```
Invalid header received from client.
```

打开cmd 使用

```
netstat -aon|findstr "XX" 
```

找到XX端口的使用情况，发现`ssr`默认运行在8080端口，在任务管理器找到对应的 `PID`  kill掉进程，重新启动tomcat即可。