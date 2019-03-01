---
title: jenkins安装
date: 2018-11-05 15:39:45
tags: [ubuntu,jenkins]
categories:
 - jenkins
 - [ubuntu,jenkins]
---
 [Jenkins](https://jenkins.io/index.html)是基于Java开发的一种持续集成工具，用于监控持续重复的工作，功能包括：  
（1）持续的软件版本发布/测试项目。  
（2）监控外部调用执行的工作。   

1. jenkins依赖于Java，首先安装Java环境
2. jenkins安装
  ```
    wget -q -O - https://pkg.jenkins.io/debian/jenkins-ci.org.key | sudo apt-key add -
    sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
    sudo apt-get update
    sudo apt-get install jenkins
  ```
3. 安装完成查看进程
  ```
    ps -ef |grep jenkins
  ```
4. Jenkins默认端口是8080，在配置文件/etc/default/jenkins中定义；
5. 启动/重启/关闭/状态
  ```
    sudo service jenkins start
    sudo service jenkins restart
    sudo service jenkins stop
    sudo service jenkins status
  ```
6. 使用配置，访问localhost:8080
  ```
  查看初始验证码
  vim /var/lib/jenkins/secrets/initialAdminPassword
  ```
7. 进入插件的界面，选择需要的插件
8. 创建用户和配置，开始使用jenkins
### 注意事项  
若登录后出现空白页面，建议使用localhost:8080/restart重启  
[jenkins入门手册](http://files.cnblogs.com/files/zz0412/jenkins%E5%85%A5%E9%97%A8%E6%89%8B%E5%86%8C.pdf)
