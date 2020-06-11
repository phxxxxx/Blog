---
title: Centos-7yum更新是报错
date: 2020-04-08 21:14:49
tags: Linux
---

​    ![](Centos-7yum更新是报错/1.jpg)

### centos7 yum 更新出现 [Errno 14] HTTP Error 404 - Not Found 的解决方法

```
yum clean all
yum makecache
```

找的资料上的解决方法，但不好使。

后来查了半天发现阿里云镜像的域名改了，于是将`etc/yum.repos.d/CentOS-Base.repo`。将域名改过来。还是不行！

后来懒得找bug遂直接将yum的源重置一遍。

## 配置方法

### 1. 备份

```
mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup
```

### 2. 下载新的 CentOS-Base.repo 到 /etc/yum.repos.d/

**CentOS 6**

```
wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-6.repo
```

或者

```
curl -o /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-6.repo
```

**CentOS 7**

```
wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo
```

或者

```
curl -o /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo
```

**CentOS 8**

```
wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-8.repo
```

或者

```
curl -o /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-8.repo
```

### 3. 运行 yum makecache 生成缓存

```c
yum clean all
yum makecache
yum -y update
```

### 4. 其他

非阿里云ECS用户会出现 Couldn't resolve host 'mirrors.cloud.aliyuncs.com' 信息，不影响使用。用户也可自行修改相关配置: eg:

```
sed -i -e '/mirrors.cloud.aliyuncs.com/d' -e '/mirrors.aliyuncs.com/d' /etc/yum.repos.d/CentO
```