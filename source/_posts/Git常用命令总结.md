---
title: 关于nodejs的npm命令无反应的解决方案
date: 2018-05-19 22:41:34
tags: 技巧
categories: 技巧
copyright: true
---

## 关于nodejs的npm命令无反应的解决方案：
看到nodejs的默认模块安装路径在c盘
于是想修改下，按命令 npm config set prefix 。
结果就遇坑了，之后我的npm命令完全无反应，不是加载的那种状态
而是下标不停地在哪里闪...
之后找解决方案，说要删除npmrc文件。
强调：不是nodejs安装目录npm模块下的那个npmrc文件
而是在C:\Users\{账户}\下的.npmrc文件.... 
## nodejs window下安装与配置淘宝镜像
1，前往nodejs官网下载安装软件，地址：https://nodejs.org/en/ 
2，点击下一步继续安装，安装完成，在命令输入：node -v,npm -v,查看版本，即是安装成功 
3，随便在计算机哪个盘建一个全局目录，比如我的在E盘：E:\nodejs\node_global 
4，设置nodejs全局目录，所有以全局安装的包都被安装在这，打开nodejs命令行窗口，

- 使用命令行设置：
```
npm config set cache "E:\nodejs\node_cache"
npm config set prefix "E:\nodejs\node_global"
```

- 设置环境变量
>>>
1.用户变量 path 中把 
C:\Users\Administrator\AppData\Roaming\npm; 
—改为—- 
E:\nodejs\node_global
2.在系统变量中 新增变量 
NODE_PATH—– E:\nodejs\node_global\node_modules
3.系统变量中 path:C:\Program Files\nodejs\; 
E:\nodejs\node_global\node_modules;

5,前往淘宝镜像官网 http://npm.taobao.org/，可查看安装cnpm包的命令
在命令行输入：
```
npm install -g cnpm --registry=https://registry.npm.taobao.org
```