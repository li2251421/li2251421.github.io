# Hugo + Github Pages 搭建个人博客


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
新建仓库 https://github.com/li2251421/li2251421.github.io



