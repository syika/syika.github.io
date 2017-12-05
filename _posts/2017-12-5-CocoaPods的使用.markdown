---
layout: post
title: 'CocoaPods的使用'
subtitle: '好久没玩儿他了~记录一些新版遇到的坑'
date: 2017-12-5
author: "syika"
catalog: true
<!-- multilingual: true -->
header-img: "img/b7003af33a87e9508f5a5bf217385343faf2b4db.jpeg"
tags:
    - iOS开发
---

> 最近一直在做Framework开发，好久没有接触CocoaPods了<br><br>
> 安装一下，顺便纪录新版本的坑~

## 简介

iOS开发时，项目中会引用许多第三方库，CocoaPods（https://github.com/CocoaPods/CocoaPods）可以用来方便的统一管理这些第三方库。对开发效率的帮助非常大，并且CocoaPods是运行下Ruby上的软件。

## 安装

### 0：
检查一下ruby的版本，Xcode5以上自带ruby环境，不用我们在安装，如果不是最新系统最好更新一下，
在终端中运行如下命令：
> $ gem update--system
<br>
你会发现不能更新，需要翻墙，不会翻墙的话就需要更换Ruby镜像的地址
在终端中运行如下命令：
> $ gem sources -l (检查镜像地址)
> $ gem sources --remove https://rubygems.org/ (移除镜像地址)
> $ gem sources -a https://ruby.taobao.org/ (新增镜像地址)
<br>
然后再更新ruby

### 1：
安装CocoaPods
在终端中运行如下命令：
> $ sudo gem install cocoa pods
<br>
嗯嗯~就是这样，你就下好了

### 2：
cd到你的项目目录下，在刚才的文件夹中创建文件Podfile
运行如下命令：
> $ vim Podfile
<br>
（i：进入编辑模式
    :wq：退出保存   "不行就：:wq!"）
<br>
低版本的cocoa pods在编写Podfile文件时这样写就可以了
platform :iOS, '8.0'
pod 'AFNetworking'
高版本的cocoa pods在编写Podfile文件必须这样写
platform :ios, '8.0'
target "targetName" do
pod 'AFNetworking'
end

### 3：
确认是你刚刚项目的总目录，然后安装
在终端中运行如下命令：
> $ pod install
<br>
如果遇到command not found这种错误
在终端中运行如下命令：
> $ sudo gem install cocoa pods -v
<br>
如果再遇到ERROR: While executing gem这种错误
在终端中运行如下命令：
> $ sudo gem install -n /usr/local/bin cocoapods
<br>
然后再安装


## 总结
果真一个东西很久不用就会逐渐忘记，一开始连一些基本的命令都不记得了<br>
所以还是要不断地捡起以前的东西来巩固自己<br>
熊瞎子掰苞米，掰一穗丢一穗，那就得不偿失了o~
