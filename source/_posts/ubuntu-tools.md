---
title: ubuntu常用工具安装
date: 2018-10-29 17:08:24
tags: ubuntu
categories: ubuntu
---
ubuntu系统上安装一些常用软件介绍
## 1. chrome浏览器
  ```bash
    sudo wget http://www.linuxidc.com/files/repo/google-chrome.list -P /etc/apt/sources.list.d/
    wget -q -O - https://dl.google.com/linux/linux_signing_key.pub  | sudo apt-key add -l
    sudo apt update
    sudo apt install google-chrome-stable
  ```
## 2. git
  ```bash
    sudo apt-get install git
    git --version //测试git是否安装成功
    //　配置全局用户名和密码
    git config --global user.name "***"
    git config --global user.email "*@*.com"
  ```
## 3. atom编译器  
  * 首先从官网下载[deb](https://atom.io/)包  
  * 切换到atom deb包所在目录,使用命令进行安装
    ```bash
      sudo dpkg -i atom-amd64.deb
    ```
  * 此时可能会遇到一些问题，需要安装一些依赖包、
  ```bash
    sudo apt-get -f install
  ```
  * 打开atom
  ```bash
    atom
  ```
## 4. terminator终端安装与配置
  * 安装
  ```bash
    sudo apt-get install terminator
  ```
  * 配置
  ```bash
    cd ~/.config/terminator/
    sudo gedit config
  ```
  * 修改配置文件
  ```config
  [global_config]
        title_transmit_bg_color = "#d30102"
        focus = system
        suppress_multiple_term_dialog = True
  [keybindings]
  [profiles]
  [[default]]
        palette = "#2d2d2d:#f2777a:#99cc99:#ffcc66:#6699cc:#cc99cc:#66cccc:#d3d0c8:#747369:#f2777a:#99cc99:#ffcc66:#6699cc:#cc99cc:#66cccc:#f2f0ec"
        background_color = "#2D2D2D" # 背景颜色
        background_image = None   
        background_darkness = 0.85
        cursor_color = "#2D2D2D" # 光标颜色
        cursor_blink = True # 光标是否闪烁
        foreground_color = "#EEE9E9" # 文字的颜色
        use_system_font = False # 是否启用系统字体
        font = Ubuntu Mono 13  # 字体设置，后面的数字表示字体大小
        copy_on_selection = True # 选择文本时同时将数据拷贝到剪切板中
        show_titlebar = False # 不显示标题栏，也就是 terminator 中那个默认的红色的标题栏
  [layouts]
  [[default]]
    [[[child1]]]
        type = Terminal
        parent = window0
        profile = default
    [[[window0]]]
        type = Window
        parent = ""
  [plugins]
  ```
## 5. Cisco VPN
#### 　一. 命令行安装与使用
  ```bash
    // 安装vpnc
    sudo apt-get install vpnc
    // vpnc命令并设置参数
    vpnc
    // ifconfig 查看 Cisco VPN 连接情况
    ifconfig
    // vpnc-disconnect 断开 Cisco VPN
    vpnc-disconnect
  ```
#### 　二. 图形界面安装与使用
  ```bash
    sudo apt-get install network-manager-vpnc network-manager-vpnc-gnome
  ```

## 6. docker
```
# 1.验证是否安装curl
  which curl
# 2.允许apt安装软件包通过https访问存储库
  sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
# 3.添加Docker的官方GPG秘钥
  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
  验证key
  sudo apt-key fingerprint 0EBFCD88
# 4.设置选择版本
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu  zesty  stable"
# 5.sudo apt-get update
  　sudo apt-get -y install docker-ce

Bionic 18.04 (LTS)
Artful 17.10
Xenial 16.04 (LTS)
Trusty 14.04 (LTS)

```
