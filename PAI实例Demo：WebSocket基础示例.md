## 前言
* Demo名称：WebSocket基础示例
* Demo效果：使用 PAI实例创建一个WebSocket基础应用，并尝试持续发布
* Demo包含：Node.js 10.16
* Demo代码：[Github地址>>>](https://github.com/TencentCloudBase/pai-mate-hello-example)
* PAI实例默认环境包含：CentOS 7.0、Nginx 1.12、域名、Let’s Encrypt SSL证书、Git、PAI Agent

## 1.登录PAI管理页面
PAI实例购买、查看、访问管理页面请查看 [PAI实例使用指南>>>](https://github.com/diablojj/pai-instance-document/blob/master/使用指南.md)

![Image text](https://github.com/diablojj/paitest/blob/master/demopng1/1.png)

打开 PAI 实例管理页面，账号、密码为该云服务器的 SSH 登录账号和密码（若忘记密码请前往腾讯云云服务器控制台修改）

## 2.使用PAI部署示例

![Image text](https://github.com/diablojj/paitest/blob/master/demopng2/2.png)

在「官方应用」内找到「WebSocket基础示例」，点击发布，等待「发布成功」

![Image text](https://github.com/diablojj/paitest/blob/master/demopng2/3.png)

点击「查看页面主页」，若看到返回信息则表示已发布应用成功

## 3.体验Demo效果

![Image text](https://github.com/diablojj/paitest/blob/master/demopng2/4.png)
```
ws.on("connect", socket => {
  console.log("connect, socket id: " + socket.id);
  let count = 0;

  socket.on("messagePing", data => {
    count++;
    socket.emit("messagePong", "receive " + count + " ping(s), response pong");
  });

  socket.on("disconnect", () => {
    console.log("disconnect socket id: " + socket.id);
  });
});
```
访问WebSocket例子示例Url（PAI实例域名 + /ping） ，点击「ping」，会发送wss请求到服务端，服务端通过wss返回一个自增的数值

## 4.修改代码然后通过PAI自定义发布

![Image text](https://github.com/diablojj/paitest/blob/master/demopng2/5.png)

修改Demo内代码，将自增变为每次加2

![Image text](https://github.com/diablojj/paitest/blob/master/demopng2/6.png)

使用PAI发布自定义发布修改后的内容，并查看效果


