# 1.Git简介

Git->分布式版本控制系统，分为本地仓库和远程仓库：

一般的工作流程如下：

1. 从远程仓库中克隆或拉取代码到本地（Clone一般是克隆别人的完整项目，Pull一般是在项目开发过程中在本地同步partner的提交到远程仓库的代码）
2. 在本地coding
3. Commit之前将代码提交到缓存区（此时均在本地）
4. 提交到本地仓库（此时仍在本地，本地的仓库中保存着提交的各个历史版本）
5. 在需要时将代码提交到远程仓库（Push，此时别的团队成员可以看到你的提交，以及你的修改，git会显示出你删除的和增加的代码）

# 2.Git的安装

## 2.1git下载

https://git-scm.com/download

![image-20230402194753063](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402194753063.png)

![image-20230402194840329](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402194840329.png)

一般只用第一个，使用命令行进行操作

## 2.2安装

![image-20230402195225814](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402195225814.png)

傻瓜式一直Next即可

# 3.Git工作流程

## 3.1git流程

![image-20230402200639144](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402200639144.png)

这几个单词就是常用的所有命令🫡

```
本地仓库：是自己电脑上的Git仓库,存放我们的代码(.git 隐藏文件夹就是我们的本地仓库)     
远程仓库：是在远程服务器上的Git仓库,存放代码(可以是github或者gitee或者公司的服务器)
工作区: 我们自己写代码(文档)的地方
暂存区: .git文件夹中的index，叫做暂存区,临时存储我们即将要提交的文件
------------
Clone：克隆，将远程仓库复制到本地仓库
Push：推送，将本地仓库代码上传到远程仓库
Pull：拉取，将远程仓库代码下载到本地仓库,并将代码克隆到本地工作区
Fetch：提取，将更新的数据提取，配合Merge使用
Merge：合并，将获取到的远程仓库的代码合并到自己的分支上
Checkout：检出，将工作区的修改放弃，或切换分支或恢复删除的文件
Commit：提交，将代码提交到分支上
Add：添加，将代码添加到暂存区
```

## 3.2初始化本地仓库

![image-20230402200228030](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402200228030.png)

![image-20230402201248140](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402201248140.png)

![image-20230402201321197](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402201321197.png)

## 3.3添加文件

### 新建文件

![image-20230402202109828](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402202109828.png)

### 命令行查看文件状态

![image-20230402202159824](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402202159824.png)

在主分支

还没有提交

未追踪文件：

​	helloWorld.txt

没东西被添加去提交，但是有未追踪的文件存在（用git add 命令去追踪）

### git add 文件名，添加文件

![image-20230402202609650](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402202609650.png)

可以输入hello，使用Tab补全（vim编辑）

### 再次查看状态

![image-20230402202752293](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402202752293.png)

绿色代表已经在暂存区

## 3.4提交至本地仓库

### git commit命令提交

![image-20230402202935871](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402202935871.png)

-m 参数表示提交的注释

### 再次查看status

![image-20230402203152200](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402203152200.png)

可使用⬆️键查看之前输入的命令（vim）

## 3.5修改，并再次提交

### modify the file

![image-20230402203356367](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402203356367.png)

### 再次查看状态

![image-20230402203442945](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402203442945.png)

红色意味着修改并未跟踪

### git diff 命令查看修改的地方

![image-20230402203608544](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402203608544.png)

### git add & git commit 再次提交

![image-20230402203815224](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402203815224.png)

## 3.6版本回退

### git log 查看日志

![image-20230402203935318](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402203935318.png)

commit后面的是提交时的版本号

也可以使用git reflog 命令获得版本号

![image-20230402204343706](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402204343706.png)

使用git reset --hard +版本号 命令来回退到想要的版本（所以提交时的注释很重要🫡）

![image-20230402204551934](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402204551934.png)

还有一些命令，git add ./ 添加所有文件，git checkout --file 丢弃工作区的修改， 还有强制推送远程仓库等等，不可能把所有的命令都记住，用的时候再搜索即可。

# 4.常见代码托管平台

```
github  基于git实现在线代码托管的仓库，向互联网开放，企业版要收钱。
gitee   即码云，是 oschina 免费给企业用的，不用自己搭建环境。
gitlab  类似 github，一般用于在企业内搭建git私服，要自己搭环境。
```

## 4.1Github

关于GitHub的简单介绍

![image-20230402215213115](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402215213115.png)

可以前往GitHub中文社区https://www.githubs.cn/

创建仓库

![image-20230402211517688](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402211517688.png)

![image-20230402211759417](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402211759417.png)

![image-20230402211826391](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402211826391.png)

GitHub告诉我们，可以从这个仓库克隆出新的仓库，也可以把一个已有的本地仓库与之关联，然后，把本地仓库的内容推送到GitHub仓库。

### 添加远程仓库

![image-20230402212243236](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402212243236.png)

### HTTPS连接

```shell
git push -u origin main
```

 经典的报错

![image-20230402213311162](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402213311162.png)

![image-20230402214431363](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402214431363.png)

尝试不同的方法，总可以解决🫡

博客链接https://www.cnblogs.com/fairylyl/p/15059437.html

首先切换分支到main分支，再使用git push 成功

![image-20230402214603031](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402214603031.png)

![image-20230402214724063](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402214724063.png)

时间是按照commit的时间，push只是将本地仓库的内容和远程仓库进行同步。

以上是GitHub采用HTTPS连接的方法，也可以采用SSH连接的方法，包括创建私钥等等，SSH可能比HTTPS更稳定（节点不稳定的情况下🫡）

GitHub这些功能简单说一下，一些大型项目用得到，包括Issues，Releases等

## 4.3Gitee

具体操作与GitHub类似

## 4.4Gitlab

总的来说就是自建Github，自己购买服务器，并配置Gitlab的服务，常用于公司，一些代码不能开源，但需要远程托管。

https://www.zhihu.com/question/354443004

# 5.IDE使用Git

## 5.1Vscode

可以下载GitLens插件，也可以不下🫡

![image-20230402221127053](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402221127053.png)

插件拥有更多功能，不过一般也用不到

![image-20230402221201805](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402221201805.png)

只需看对应文件夹的修改即可

![image-20230402221311813](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402221311813.png)

查看变更

![image-20230402221411494](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402221411494.png)

点击提交按钮，获得的提交信息

更详细的操作可以去看这些类似的博客

https://zhuanlan.zhihu.com/p/276376558

不过一般IDE里面进行提交比用命令行要慢一点，看个人喜好在哪里进行版本控制，我只是做个示例。

## 5.2VS

![image-20230402221740555](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402221740555.png)

![image-20230402221943795](C:\Users\liuya\AppData\Roaming\Typora\typora-user-images\image-20230402221943795.png)
