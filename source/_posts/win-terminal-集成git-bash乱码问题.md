---
title: win terminal 集成git-bash乱码问题
date: 2020-10-27 15:26:53
tags: terminal
---

### Microsoft Terminal(vs code)中集成git-bash时中文显示乱码

作者：路过麦田
链接：https://www.jianshu.com/p/123cde9c93da
来源：简书

### 解决`vs code`中集成git-bash乱码问题

   在设置中找到下面的设置项，如果不好找的话，直接在搜索框中搜索`env.windows`关键字即可。在弹出的搜索结果中点击`Edit in settings.json`即可进行编辑。

* `terminal.integrated.shell.windows`项为`git-bash`的路径

* `terminal.integrated.env.windows`项为启动时自动设置的环境变量

```bash
"terminal.integrated.shell.windows": "D:\\App\\Git\\bin\\bash.exe",
"terminal.integrated.env.windows": {"LC_ALL":"en_US.UTF-8"},
```

按照上述方式设置后，就可以正常显示中文了。

### 解决`microsoft terminal`中集成git-bash乱码问题

我在官方文档中找了一圈也没有找到可以设置环境变量的地方，看来在`microsoft terminal`中设置是 无法实现了，但是可以在git的`.bashrc`文件中设置，下面换了一种思路，直接在git的配置中设置环境变量

我在windows的Home目录下并没有找到关于git-bash的配置文件`.bash_profile`，全局搜索了一下好像也没有，没办法，只能改git-bash的安装目录下的配置文件了

打开`D:\App\Git\etc\bash.bashrc`文件（就在安装目录下的etc文件夹中），然后在末尾加入

```shell
export LC_ALL=en_US.UTF-8    
```

保存后，重新打开`microsoft terminal`终端后，`git log`就可以正常显示中文了

同时，上述方法也可以试用于`vs code`

其实，说到底，还是将该环境变量写到了文件中，只不过不是写到了系统的环境变量中，而是git自身的配置文件中。




