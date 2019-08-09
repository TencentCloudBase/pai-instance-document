## 前言
* Demo名称：小程序商城
* Demo效果：使用PAI实例 5 分钟搭建一个小程序商城
* Demo包含：Node.js 10.16、Sqlite 3.7、NideShop（开发者 tumobi）
* Demo代码：[NideShop服务端](https://github.com/TencentCloudBase/pai-template-nideshop)、[NideShop小程序端](https://github.com/tumobi/nideshop-mini-program)
* PAI实例默认环境包含：CentOS 7.0、Nginx 1.12、域名、Let’s Encrypt SSL证书、Git、PAI Agent

## 1.登录PAI管理页面
PAI实例购买、查看、访问管理页面请查看 [PAI实例使用指南>>>](https://github.com/diablojj/pai-instance-document/blob/master/使用指南.md)

![Image text](https://github.com/diablojj/paitest/blob/master/demopng1/1.png)

打开 PAI 实例管理页面，账号、密码为该云服务器的 SSH 登录账号和密码（若忘记密码请前往腾讯云云服务器控制台修改）

## 2.使用PAI部署服务端
### 2-1.在PAI管理页发布Demo「官方实例-小程序商城」

![Image text](https://github.com/diablojj/paitest/blob/master/demopng1/2.png)

在「官方示例」内找到「小程序商城 NideShop」，点击「发布」，弹出「任务窗口」，等待「发布成功」

### 2-2.检查成功

![Image text](https://github.com/diablojj/paitest/blob/master/demopng1/4.png)
![Image text](https://github.com/diablojj/paitest/blob/master/demopng1/5.png)

点击「查看页面主页」，若查看到接口返回信息则表示服务以部署成功


## 3.配置小程序端
### 3-1.下载小程序端源码
https://github.com/tumobi/nideshop-mini-program

从NideShop官方GitHub地址下载即可

### 3-2.导入项目到微信
将项目导入微信IDE

### 3-3.修改config内服务器域名
![Image text](https://github.com/diablojj/paitest/blob/master/demopng1/7.png)

修改 config/api.js 内 ApiRootUrl 为您的PAI实例实际的服务器域名

### 3-4.修改小程序信任的服务器域名
小程序端会校验其访问域名是否为您在微信开放平台内填写的信任域名（[详细信息见>>>](https://developers.weixin.qq.com/miniprogram/dev/framework/ability/network.html
)），有两个方法可以通过校验，

#### I.前往「微信开放平台-开发-开发设置-服务器域名」填写PAI实例域名
#### II.在微信IDE内关闭校验

![Image text](https://github.com/diablojj/paitest/blob/master/demopng1/6.png)


## 4.体验Demo效果

![Image text](https://github.com/diablojj/paitest/blob/master/demopng1/8.png)

编译小程序端后，左侧预览界面展示 NideShop 小程序商城的首页，您已成功搭建一个小程序商城

想创建一个您自己的小程序商城？请复制 Demo 到您的 Git 账号内，修改任意内容，再次通过PAI自定义发布即可
