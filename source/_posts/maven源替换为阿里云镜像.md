---
title: maven源替换为阿里云镜像
date: 2020-09-30 15:53:52
tags: Java
---

## 解决IDEA的maven依赖下载速度慢的问题

* 使用阿里云的maven镜像
* 新建settings.xml,将以下代码替换进去

```xml
<mirrors>
     <mirror>
          <id>alimaven</id>
          <name>aliyun maven</name>
          <url>http://maven.aliyun.com/nexus/content/groups/public/</url>
          <mirrorOf>central</mirrorOf>
      </mirror>

      <mirror>
          <id>uk</id>
          <mirrorOf>central</mirrorOf>
          <name>Human Readable Name for this Mirror.</name>
          <url>http://uk.maven.org/maven2/</url>
      </mirror>

      <mirror>
          <id>CN</id>
          <name>OSChina Central</name>
          <url>http://maven.oschina.net/content/groups/public/</url>
          <mirrorOf>central</mirrorOf>
      </mirror>

      <mirror>
          <id>nexus</id>
          <name>internal nexus repository</name>
          <url>http://repo.maven.apache.org/maven2</url>
          <mirrorOf>central</mirrorOf>
      </mirror>
</mirrors>
```

