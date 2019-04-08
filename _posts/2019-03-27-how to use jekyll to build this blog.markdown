---
layout: post
title: 使用jekyll从零开始搭建这个博客
# date: 2019-03-27 19:14:00
categories: how to
tags: how to,jekyll,blog
---

## **前言**

该博客部署在阿里云上，评论模块采用[Valine](https://valine.js.org/)，这篇博文主要介绍如何从零开始搭建这个博客

## **步骤**

### **1、更新系统yum源**
```shell
sudo yum update
```
### **2、安装rvm**
```shell
gpg2 --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB

curl -sSL https://get.rvm.io | bash -s stable

source the-path-to-rvm/scripts/rvm
```
安装完成后输入rvm -v，检验是否安装成功

### **3、安装ruby(2.6.1)**
```shell
rvm install 2.6.1

rvm 2.6.1 --default
```
检查安装是否成功
```shell
ruby -v

gem -v
```
### **4、安装jekyll、bundler**
```shell
gem install jekyll、bundler
```
### **5、安装依赖**
上传源码到服务器
```shell
cd path-to-your-project
bundle install
```
### **6、集成Valine评论模块**
参照[Valine官网](https://valine.js.org/quickstart.html)集成评论模块，并
在_config.yml中配置自己的valine_comment参数
### **7、运行**
```shell
cd path-to-your-project
bundle exec jekyll serve
```
## **部署过程中遇到的问题**

>post文件名中包含中文导致博文乱码

解决方案

>jekyll貌似不支持post文件名中带中文，可以通过在post的元参数title中设置中文标题来规避这个问题



