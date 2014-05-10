---
layout: post
title: "使用GitHub Pages创建一个属于你自己的私人博客"
tagline: ""
keywords: "使用GitHub Pages创建一个属于你自己的私人博客,GitHub,Git,GitHub Pages,SSH,Blog,博客"
description: ""
category: other
tags : [Git, GitHub]
---
{% include JB/setup %}

Github作为现在最流行的代码仓库，已经得到很多大公司和项目的青睐，比如jQuery、Twitter等。
为使项目更方便的被人理解，介绍页面少不了，甚至会需要完整的文档站，Github替你想到了这一点，
他提供了Github Pages的服务，不仅可以方便的为项目建立介绍站点，也可以用来建立个人博客。





**使用GitHub Pages的几个优点：**

- 轻量级的博客系统，没有麻烦的配置。
- 使用标记语言，比如Markdown。
- 无需自己搭建服务器
- 根据Github的限制，对应的每个站有300MB空间。
- 可以绑定自己的域名。

**当然GitHub Pages也有自己的缺点：**

- 使用Jekyll模板系统，相当于静态页发布，适合博客，文档介绍等。
- 动态程序的部分相当局限，比如没有评论，不过还好我们有解决方案。
- 基于Git，很多东西需要动手，不像Wordpress有强大的后台。

**以下所有操作都是基于Windows操作系统环境。**

## 注册GitHub账号

使用[GitHub](https://github.com "GitHub")托管代码，必须现在[GitHub](https://github.com)上注册一个账号。

## 安装Git

[下载Git for Windows](http://git-scm.com/downloads "下载Git for Windows")，使用默认安装，安装完成后即可使用Git。

## 配置和使用GitHub

打开 Git Bash

### 1、检查SSH key设置

查看自己电脑上的SSH key设置：

        $ cd ~/.ssh

如果提示为“No such file or directory”，直接跳到第三步，否则继续。

### 2、备份以及删除旧的SSH key

为了保险起见，先备份后再重新生成：

        $ ls
        config  id_rsa  id_rsa.pub  known_hosts
        $ mkdir key_backup
        $ cp id_rsa* key_backup
        $ rm id_rsa*

### 3、生成新的SSH key

填写你自己的GitHub邮件地址，提示要输入信息的地方直接回车就OK：

        $ ssh-keygen -t rsa -C "邮件地址@youremail.com"
        Generating public/private rsa key pair.
        Enter file in which to save the key (/Users/your_user_directory/.ssh/id_rsa):

把生成的key文件复制到C:\Documents and Settings\Administrator\\.ssh\目录下。
必须把id_rsa、id_rsa.pub这两个文件放到当前用户目录的“.ssh”目录下才能生效。
在windows中只能在命令行下输入创建“.”开头的文件夹，命令为：

        $ mkdir .ssh

### 4、GitHub SSH key设置

设置Git用户信息
第一个要配置的是你个人的用户名称和电子邮件地址。这两条配置很重要，每次 Git 提交时都会引用这两条信息，说明是谁提交了更新，
所以会随更新内容一起被永久纳入历史记录，用户名称必须是你GitHub真实的账号名称：

        $ git config --global user.name "username"
        $ git config --global user.email lisan@example.com

Git和GitHub之间使用SSH连接，必须在GitHub上设置好key，才能正常连接。

进入GitHub主页，进入账号设置：
![setting](/images/githubpages/github-setting.jpg)
点击左侧SSH keys选项，点击Add SSH key，然后打开C:\Documents and Settings\Administrator\\.ssh\目录下id_rsa.pub文件，
复制里面的内容粘贴到key文本框中，点击保存即可：
![add ssh key](/images/githubpages/add-sshkey.jpg)

### 5、测试SSH连接

输入下面命令测试SSH连接是正常：

        $ ssh -T git@github.com

提示以下信息，表示SSH连接成功：

        $ ssh -T git@github.com
        Hi username! You've successfully authenticated, but GitHub does not provide shell access.