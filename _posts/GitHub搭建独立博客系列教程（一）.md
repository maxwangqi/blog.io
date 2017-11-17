---
layout: post
title: GitHub搭建独立博客系列教程（一）
date: 2017-11-17
categories: blog
tags: [github,git,blog]
description: GitHub搭建独立博客系列教程
---



# GitHub搭建独立博客系列教程（一）

最近闲来无事搭建了一个个人独立博客：maxwangqi.com   现抽时间将搭建博客详细步骤记录下来。



#### 目录

**1.Github内容**

**2.购买域名**

**3.GitHub Pages搭建博客**

**4.域名与GitHub Pages空间绑定**

**5.GitHub desktop管理博客**



#### 独立博客系列教程（一）——GitHub内容

本部分教程主要介绍四个方面 **GitHub注册**、**安装Git，Node.js**、**Git与GitHub连接**



##### GitHub注册

GitHub账号注册是非常简单的，与平常网站应用注册步骤相差无几。

访问网站：https://github.com

注册账号需要填写Username，Email，Password。在这里我们需要注意的是GitHub网站中每个人Username都是唯一作为ID存在的，不存在重复Username。（例如：我的GitHub账号昵称 maxwangqi，我的GitHub Id就是maxwangqi 。）邮箱很重要，GitHub很多通知都是通过邮箱发送给用户。



#####安装git，Node.js#####

访问git网站：https://git-scm.com/downloads ，选择操作系统安装版本，按照提示安装git。

安装完成后，还需要最后一步设置，在命令行输入：

`$ git config —global user.name "Your Name"`

``$ git config —global user.email "email@example.com"``



同样访问Node.js网站：https://nodejs.org/en/ ，按照提示安装Node.js。



##### Git与Github连接

我们假设电脑以前并未存在ssh key

###### 1.生成SSH key######

``1.ssh-keygen -t rsa -C "邮箱地址@youremail.com"``

``2.Generating public/private rsa key pair.``

``3.Enter file in which to save the key (/Users/your_user_directory/.ssh/id_rsa)``



这时候系统会要求设置密码，一般直接Enter键不设置，后面确认密码同样如此。

``1.Enter passphrase (empty for no passphrase):``

``2.Enter same passphrase again:``



最后看到这样的界面，就成功设置ssh key:	![ssh key](http://oz4sklljr.bkt.clouddn.com/ssh-key-set.png)



###### 2.添加到SSH Key到GitHub######

在本机设置生成SSH Key成功后，需要将SSH Key添加到GitHub中，完成SSH链接设置。



首先需要打开本机上id_rsa.pub文件，复制该文件中文本内容。



在自己Github主页中打开setting



选择SSH Key目录，将复制文本内容粘贴进去，然后点击确定即可。

![ssh key github](http://oz4sklljr.bkt.clouddn.com/ssh.jpg)	



###### 3.测试成功######

输入以下指令，查看设置是否成功：

``1.$ ssh -T git@github.com``



Enter键入出现下面内容：

``1.The authenticity of host 'github.com (207.97.227.239)' can't be established.``

``2.RSA key fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48.``

``3.Are you sure you want to continue connecting (yes/no)?``



然后输入

``yes``



出现下面情况即连接成功：

``Hi <em>username</em>! You've successfully authenticated, but GitHub does not provide shell access.``

