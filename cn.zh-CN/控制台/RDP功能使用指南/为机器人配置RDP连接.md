为机器人配置RDP连接 
================================

此文档主要介绍RDP功能的基础配置，目前仅专有云RPA服务支持RDP功能。
**注意**

使用阿里云RPA的RDP功能，需自行准备远程桌面资源，本文仅限介绍 **RPA专有云服务** 中RDP相关的基础配置，配置完成后，才能通过RDP形式调度机器人应用。

配置步骤 
-------------------------

1. 准备一个远程桌面资源，注意记录 **计算机IP、** **用户名、** **登录密码** ，确认此配置可以正常连接远程桌面，如下图，通过WINDOWS自带的远程桌面连接功能，配置好登录信息后，能够正常地登录到远程桌面上。并在远程桌面上登录机器人客户端。

![远程桌面_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6878741261/p275543.png)![远程桌面_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6878741261/p275548.png)

2. 登录RPA控制台，点击机器人监控-监控列表-选择远程桌面上登录的机器人，点击操作-配置RDP，进入RDP配置界面。

![RDP配置_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6878741261/p275585.png)

3. 设置好计算机IP、用户名、登录密码，端口名一般使用默认的3389，远程机器名称可自行定义，然后点击测试按钮，浏览器将会弹窗链接远程桌面。确认成功连上远程桌面后，证明RDP配置成功，关闭弹窗，点击确定按钮即可。
**注意**



1. 此处弹窗可能会被浏览器拦截，请取消拦截。

2. 此设置中的3389端口请不要随意更改，需要更改请联系对应网络管理员。

![RDP配置_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6878741261/p275600.png)
**说明**

给对应机器人人配置完RDP后，才能够在计划任务中使用RDP功能。请确认已严格按照上诉操作进行配置。



