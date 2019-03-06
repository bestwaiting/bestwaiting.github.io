---
title: Mac环境
date: 2018-11-02 11:47:02
tags: [Mac,Redis,iterm]
categories:
 - [Mac,Redis]
 - [Redis]
 - [iterm]
---
Mac下安装开发常用工具介绍，Redis，MySQL等
<!--- more -->

### 1. Mac通过brew安装Redis
```
1. home-brew安装
  brew install redis
2. 启动Redis服务
  brew services start redis
3. 关闭Redis服务
  brew services stop redis
4. 重启Redis服务
  brew services restart redis
5. 启动Redis客户端
  redis-cli
```
### 2. Mac配置iterm克隆会话功能
1. 打开iterm的preferences的profiles模块，修改working directory中选择reuse previous session's directory
2. 配置vi ~/.ssh/config
```
host *
ControlMaster auto
ControlPath ~/.ssh/master-%r@%h:%p
```
此时登录会话时，在.ssh目录下会有"master-\*的sock文件"
3. 配置 vi /etc/ssh/ssh_config
```
Host * ControlMaster auto ControlPath ~/.ssh/master-%r@%h:%p
```
