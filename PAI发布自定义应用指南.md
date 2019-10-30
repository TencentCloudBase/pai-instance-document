## 前言

PAI实例的「一键发布」功能提供了快速发布后台应用的能力，可以极大的提升研发效率。
本章将介绍PAI发布机制的原理，以及详细发布配置文件说明，最后提供一些官方PAI项目

## PAI发布机制

PAI实例的发布能力依赖两个信息：
* 应用代码所在的Git Repo地址
* Git Repo地址根目录下对应的 .pai.yml 文件，其中包含应用管理的执行命令

以「发布」为例，当在PAI管理页上点击「发布」时，会执行以下操作：
* 1.拉取Git项目所有文件
* 2.执行 .pai.yml 内 start 部分的脚本内容


## 配置文件.pai.yml说明
```
deployScripts:
  start:
    - npm install
    - npm run start
  delete:
    - npm run stop
  restart:
    - npm install
    - npm run restart
```
以一个 Node.js 的PAI发布配置文件为例
* deployScripts：应用管理相关脚本目录
* start：启动应用脚本内容
* delete：删除应用脚本内容
* restart：重启应用脚本内容

## PAI官方参考配置

* Node.js：https://github.com/TencentCloudBase/pai-mate-hello-example
* Go：https://github.com/TencentCloudBase/pai-mate-hello-example-go
* Python：https://github.com/TencentCloudBase/pai-mate-hello-example-py

您可以参考对应语言的官方Demo，然后在自己的项目内加上对应 .pai.yml 文件，根据实际情况微调脚本内容，就可以将存量项目改造成支持PAI发布的项目了
