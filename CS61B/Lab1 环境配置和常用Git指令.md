# Lab1 配置环境和常用Git指令

## 下载并安装Java和Git

### 下载并安装

<https://sp18.datastructur.es/materials/lab/lab1setup/windows.html>

下载并安装Java、Python(optional)、Git

> 注意在开始界面框选"Add Python to PATH"

### 终端指令+测试安装结果

<https://sp18.datastructur.es/materials/lab/lab1setup/lab1setup>

学会简易的终端指令, cd, pwd, ls, mkdir, cp, mv。

测试运行：

- java
- python -i
- git --version
- javac HelloWorld.java
- java HelloWorld

> 注意将java和javac配置到PATH中，上面第二个链接内有完整教程。

## 使用Java和Git

<https://sp18.datastructur.es/materials/lab/lab1/lab1>

### Java

javac HelloWorld.java
java HelloWorld

### Git

<https://sp18.datastructur.es/materials/guides/using-git.html>

#### 简介

Git本身是分布式版本控制系统，其中“版本控制系统”相当于游戏中的快速存档功能，“分布式”表示每个开发人员的计算机上都存储有整个项目的完整版本，即使不连互联网也能在本地使用Git。

#### 本地存储库

基本指令：

1. git init  初始化git存储库
2. git status  查看文档情况
3. git add [文件名]  将文件添加到缓存区
4. git commit -m "[添加信息]"  将缓存区内容提交到仓库中，并添加注释
5. git log 查看提交记录 （log内容太多时使用 git log --oneline精简表达）
6. git show [log中显示的Hash结果]  查看更改内容
7. git checkout [Hash结果] [文件名]  穿越时空，回到commit的地方查看文件内容。

其他指令：

1. git reset HEAD [文件名]  把文件从缓存区中移出去（撤销add操作）
2. git commit --amend  合并到上一次commit上去

#### 远程存储库

基本指令：

1. git remote add [仓库名] [仓库地址]  添加远程仓库的地址
2. git remote -v  显示所有远程仓库库
3. git clone [仓库地址]  制作远程仓库的副本
4. git pull [仓库名] [master]  获取文件的最新副本
5. git push [仓库名] [master]  将本地文件推送到远程仓库中去

（常用的一般就git push了）

附带设置SSL连接的指令：

1. git config -global user.name "AAA"
2. git config -global user.email "AAA@B.com"  设置全局信息
3. ssh-keygen -t rsa
4. 到.ssh目录下找到id_rsa.pub文件，将全部内容复制到Gtihub-Settings-SSH and GPG keys-new SSH key的框内，点击add SSH key即可
5. ssh -T git@github.com 检测是否设置成功

设置完成后走SSH连接就不需要输入账号和密码，实际使用会方便很多。

#### Git分支

1. git branch [新分支名]  新建分支
2. git checkout [分支名]  进入分支中
3. git checkout -b [新分支名]  新建分支并进入其中
4. git branch -m [旧分支名] [新分支名]  重命名
5. git branch -d [分支名]  删除分支
6. git branch  显示分支信息（-v可额外显示最后一次提交信息）
7. git merge [分支B]  将分支B合并到当前分支上

> merge冲突时，需打开文件**手动修改**。

## 章末小结

### 我学到了什么？

- Git的本地存储库的使用方法
- Git的远程存储库的使用方法
- Git的SSH连接建立方法
- Git分支操作，新建删除命名合并，以及merge冲突时需手动更改。

### 如何学会的？

- 用Git去解决实际问题，如交作业、存放Notes等，学习之后投入实践，遇到问题就去查阅资料解决问题。

### 怎么类推出去？

- 学习不是为了掌握工具，而是为了解决实际问题，学一门新工具的同时，也要注重运用其进行实践。
