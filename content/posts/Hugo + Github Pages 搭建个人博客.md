---
title: "Hugo + Github Pages 搭建个人博客"
date: 2021-04-25T09:43:24+08:00
featuredImage: "/images/hugo.png"
draft: false
---

LoveIt 主题，简洁优雅高效，聚焦博客编写

<!--more-->

## 安装hugo
https://github.com/gohugoio/hugo/releases
```shell script
hugo version
hugo v0.82.1-60618210+extended windows/amd64 BuildDate=2021-04-20T11:02:50Z VendorInfo=gohugoio
```

## 创建站点并选择主题
本人选择的是LoveIt主题
```shell script
cd E:\project
hugo new site blog
cd blog
git init
git submodule add https://github.com/dillonzq/LoveIt.git
cp themes/LoveIt/exampleSite/config.toml config.toml
```

## 修改配置本地启动
```shell script
vim config.tomal
hugo serve -e production
```
http://localhost:1313查看效果

## 发布到github
- 新建仓库 https://github.com/li2251421/li2251421.github.io
- 设置发布目录为docs(publishDir = "docs")
- hugo命令生成网页
- push 到 github
- 设置github pages，目录选择docs，绑定域名blog.kepreal.com

## Reference
- https://hugoloveit.com/zh-cn/
- https://hugoloveit.com/zh-cn/theme-documentation-basics/
- https://zhuanlan.zhihu.com/p/37752930

