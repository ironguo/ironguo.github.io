---
layout: post
title: "使用GitHub Pages创建一个属于你自己的私人博客"
tagline: ""
description: "GitHub Pages Git 博客"
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

使用GitHub托管代码，必须现在GitHub上注册一个账号。

## 安装Git

下载Git for Windows，使用默认安装，安装完成后即可使用Git。

## 配置和使用GitHub

打开 Git Bash

### 1、检查SSH key设置

检查自己电脑的SSH 可以设置：

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

把生成的key文件复制到C:\Documents and Settings\Administrator\.ssh\目录下。
必须把这两个文件放到当前用户目录的“.ssh”目录下才能生效。
在windows中只能在命令行下输入创建“.”开头的文件夹，命令为：

        $ mkdir .ssh



