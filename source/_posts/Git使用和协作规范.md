---
title: Git使用和协作规范
date: 2020-02-24 21:09:45
tags: Git
---

## Git的使用

### 基础命令

* `git init `
* `git add .`
* `git commit -m "the record"`
* `git log`
* `git log --graph`
* `git status`
* `git push origin maste`

<b>以上均为最常用的命令，不加备注了 </b>

----------

### 常用命令

* `git reset --hard HEAD^`

  将文件退回到上一个版本，同时可以使用`git reset --hard id`来退回到制定的版本。

* `git reflog`  

  可以查看之前所有的命令。`git log`只能查看最近三次提交的记录。

* `git diff HEAD -- readme.txt`

  查看工作区和版本库里面最新版本的区别。

* ``git checkout -- file`

  可以丢弃工作区的修改。注意  `--` ,不然会是另外一个命令。其实是用版本库里的版本替换工作区的版本，无论工作区是修改还是删除，都可以“一键还原”。

* `git remote add origin git@github.com:phxxxxx/learngit.git`

  关联到远程仓库，记得添加ssh公钥。

* `ssh-keygen -t rsa -C "youremail@163.com"`

  生成SSH密钥。目录为/user/.ssh/

* `git clone git@github.com:phxxxxx/repo_name.git`

  从远程库克隆一份。

* `git pull`,从远端克隆一份并合并到当前分支。

------

### 分支管理

#### 创建分支与合并分支

* `git branch dev`

  创建dev分支。`dev`分支的工作完成，我们就可以切换回`master`分支。

* `git checkout dev`  

  切换分支。`git checkout -b dev` 创建并切换分支。

* `git branch`

  列出当前所有分支，当前分支前面会标一个`*`号。

* `git merge`

  用于合并指定分支到当前分支，首先切换回`master`分支，然后合并。

* `git branch -d dev`

  删除指定分支。因为创建、合并和删除分支非常快，所以Git鼓励你使用分支完成某个任务，合并后再删掉分支，这和直接在`master`分支上工作效果是一样的，但过程更安全。

---

Git鼓励大量使用分支：

查看分支：`git branch`

创建分支：`git branch `

切换分支：`git checkout `或者`git switch `

创建+切换分支：`git checkout -b `或者`git switch -c `

合并某分支到当前分支：`git merge `

删除分支：`git branch -d `

------

### 分支管理策略

`master`分支应该是非常稳定的，也就是仅用来发布大的版本更迭，平时不能在上面干活；

#### 干活都在`dev`分支上

也就是说，`dev`分支是不稳定的，到某个时候，比如1.0版本发布时，再把`dev`分支合并到`master`上，在`master`分支发布1.0版本；

每个人都在`dev`分支上干活，每个人都有自己的分支，时不时地往`dev`分支上合并就可以了。

------

#### 改bug另外开分支

1. `git stash` 首先储存当前未完成任务。
2. `git switch branch` 在哪个分支修改就在哪个分支创建分支。
3. `git switch master` 切换回原来的分支。
4. `git merge --no-ff -m "merged bug fix 101" `合并分支。
5. `git stash pop` ,恢复原先工作分支内容。并删除stash存储内容。
6. ``git cherry-pick`若当前分支也有相同的bug，就不需要在dev分支上手动再把修bug的过程重复一遍。

------

具体详细步骤参照  [Click here](https://segmentfault.com/a/1190000015798490)

#### 步骤1：从GitHub上克隆项目，创建分支到本地

同样输入命令
`git clone git@github.com:phxxxxx/TARS_HERO.git`

输入给git branch后你会发现并没有所有的分支，所以要`创建远程仓库的分支到本地`
比如我是Bob，输入命令
`git checkout -b Bob origin/Bob`
这样就可以在自己的分支上进行项目了

#### 步骤2：参与修改项目

举个实践的例子，在test目录下创建一个文本吧，随便写什么，我弄了Hello.txt
接下来跟正常步骤一样，提交分支
`git add Hello.txt`
`git commit -m"提交Hello.txt"`

然后把分支合并到master上（开发中一般是dev作为开发线，master作为主版本，这里就简化吧）
`git checkout master`
`git merge --no-ff -m"写合并分支的commit" Bob`
以上步骤先切换到master，再把Bob分支合并到master，并且不删除Bob分支

接下来推送master到远程仓库（当然也可以把自己的分支推送上去）
`git push origin master`
`git push origin Bob`











