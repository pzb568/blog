---
title: MYSQL数据库使用记录
categories:
    - 软件工具
tags:
    - MYSQL
    - 数据库
keywords:
    - MYSQL
abbrlink: 1f77a6f0
date: 2019-07-07 09:12:35
---
## 查看数据库版本
```
SELECT @@VERSION;
```
## 查看数据库
```
show databases;
```
## 查看用户
```
select user();
```
## 查看用户权限
```
show grants;
```
## 创建数据库
```
create database wordpress;
```
## 删除数据库
```
drop database wordpress;
```
<!--more-->
