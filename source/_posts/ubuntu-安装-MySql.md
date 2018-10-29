---
title: ubuntu 安装 MySql
date: 2018-10-29 19:13:04
tags: [ubuntu,mysql]
categories: [ubuntu,mysql]
---
mysql安装步骤及注意事项
### 1. 安装mysql
```
sudo apt-get install mysql-server mysql-client
```
### 2. 查看mysql是否安装成功
```
netstat -tap | grep mysql
```
### 3. 登录mysql
```
mysql -u root -p
```
### 错误解决方案
```
如提示不能登录的话，启用安全模式绕过密码登录，然后修改密码
  sudo /etc/init.d/mysql stop
  sudo /usr/bin/mysqld_safe --skip-grant-tables --skip-networking &
如提示mysqld_safe Directory ‘/var/run/mysqld’ for UNIX socket file don’t exists
  sudo mkdir -p /var/run/mysqld
  sudo chown mysql:mysql /var/run/mysqld
```
### 4. 修改密码
```
UPDATE mysql.user SET authentication_string=PASSWORD('root'), plugin='mysql_native_password' WHERE User='root';
flush privileges;
```
### 5. 验证登录
```
sudo /etc/init.d/mysql start
mysql -u root -p
```
