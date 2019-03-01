---
title: hexo安装
date: 2018-10-29 17:03:16
tags: Hexo
categories: Hexo
---
本文主要介绍使用hexo＋github搭建个人博客，可以定制属于自己的小空间，不受限于blog平台限制。现在开始介绍搭建博客的步骤:(这里只介绍最基本的博客搭建过程，至于博客个性化另行研究哦～～～)

### 1. 安装git
### 2. 安装npm
### 3. 安装hexo
```bash
  sudo npm install hexo-cli -g
```
### 4. 初始化hexo
```bash
  hexo init blog（目录）
  cd blog
  hexo clean //清楚缓存
  hexo g //重新生成服务
  hexo s //本地服务部署
```
### 5. 设置主题
```bash
  git clone https://github.com/iissnan/hexo-theme-next themes/next
```
  修改_config.yml文件中theme字段为next,同时设置scheme  
  （1）Muse - 默认 Scheme，这是 NexT 最初的版本，黑白主调，大量留白  
  （2）Mist - Muse 的紧凑版本，整洁有序的单栏外观  
  （3）Pisces - 双栏 Scheme，小家碧玉似的清新  
### 6. 申请github账号，创建新代码库(用户名.github.io)
### 7. 修改_config.yml文件中deploy字段下配置
### 8. 部署到github
```bash
  hexo d //部署生成静态文件到github
```
如果命令不支持的话，安装npm deployer插件
```bash
  npm install hexo-deployer-git --save
```
