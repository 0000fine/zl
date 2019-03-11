## **1.项目名称：基于Arduino UNO开发板的童车倒车报警系统**
## 开发环境：Arduino UNO开发板+HC-SR04模块+LCD1602+光敏电阻+蜂鸣器+LED灯+马达驱动器
项目描述：该项目主要利用Arduino软件编写HC-SR04（超声波模块）、LCD1602、蜂鸣器、LED灯、马达驱动器和光敏电阻的代码，将已完成的代码烧录到Arduino UNO开发板中，HC-SR04（超声波模块）会检测车后方的实时距离并显示在LCD1602屏幕上，当距离小于20厘米时，蜂鸣器、LED（红）灯、会发出警报并且由马达驱动器驱动的车轮也会停止转动以保证童车的安全。光敏电阻检测到亮度为暗时，自动打开车LED（白）灯。
<br>如图所示：
![](https://github.com/0000fine/1032303971-qq.com/blob/Photos/%E4%BB%BF%E7%9C%9F%E5%9B%BE.png) 



## **2.mysql服务设置远程连接 解决1251 client does not support ..问题**
## 一、前期准备
1、虚拟机/物理机    mysql环境（非本机）
<br>2、本机 navicat软件（验证远程连接）
## 二 、mysql配置
1、在远程主机的本机   使用root用户连接mysql
* 命令：mysql -u root -p
* 备注 ： mysql -u 最高权限用户名 -p   再输入密码进入
<br>2、设置用户配置项
<br>(1) 查看用户信息
* select host,user,plugin,authentication_string from mysql.user;
* 备注：host为 % 表示不限制ip   localhost表示本机使用    plugin非mysql_native_password 则需要修改密码
<br>(2)修改用户密码
* ALTER USER 'root'@'%' IDENTIFIED WITH mysql_native_password BY 'newpassword'; 
* 备注：更新一下用户的密码 root用户密码为newpassword



## **3.mysql数据库学习笔记**
### 数据库：
数据库对象：如：表、视图、存储过程、事件、查询、函数、报表和触发器等...
RDBMS 关系数据库管理系统:     
* 表（table）
* 数据库（database）
* 列（字段）
* 行（记录）
* 主键（唯一）
* 外键（关联两个表）
* 索引（目录）
### 基础命令：
* create database 数据库名;  创建
* drop database 数据库名； 删除
* show databases； 查看数据库
* use 数据库名； 使用数据库
* show tables； 查看表
### 字符集：（因为计算机只能识别二进制）
* ASSCII: 文字符号.（ANSI 20世纪60年代） ISO-646
* Unicode: (全世界语言、文字和符号) ISO-10646
* UTF-16
* UTF-8
* 汉字常见字符集：GB2312 GB13000 GBK GB18030
### 存储引擎：（5.5版本）
分类：
* MYISAM：不支持事务、外键，但是访问速度快;<br>INNODB:支持事务提交、回滚和崩溃恢复，但是占空间大（保留数据与索引） 5.5版本默认选择
* MEMORY:使用内存存储 * *.frm*  优点：访问速度快  缺点：服务器关闭，数据丢失，表存在.
* **事务：是指作为单个逻辑单元执行的一系列操作，要么完全执行，要么完全不执行.**
* **扩展名：<br> *.frm*:存储表定义 *MYD*:（MYData，存储数据）*MYI*:(MYIndex，存储索引) **
### SQL：（结构化查询语言）数据库语言
<br> 分类：
|* DDL（数据定义语言）：定义数据库对象，创建库、表、列等.
|———————————————————————————————————————————|
|* DML（数据操作语言）：操作表中的记录.
|———————————————————————————————————————————|
|* DQL（数据查询语言）：查询数据库.
|———————————————————————————————————————————|
|* DCL（数据控制语言）：用来定义访问控制权限和安全级别.
|———————————————————————————————————————————|

