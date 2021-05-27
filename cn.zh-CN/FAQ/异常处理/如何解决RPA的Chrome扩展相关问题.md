如何解决RPA的Chrome扩展相关问题 
=========================================

本文主要介绍阿里云RPA涉及的Chrome扩展插件常见问题及解决方法。

一、什么是Chrome扩展程序？ 
-------------------------------------

Chrome扩展程序是一个可以修改和增强Chrome浏览器功能的小型软件程序。阿里云RPA需要借助Chrome扩展程序来实现Chrome的自动化操作。

二、阿里云RPA插件常见问题及解决方法 
----------------------------------------



### 1. 第一次安装插件 

如果首次安装扩展插件，Chrome插件管理会提示"错误"，需要配置使插件生效。

a. 打开浏览器，点击浏览器右上角的"错误"按钮，然后点击"已添加新扩展程序（Alibaba Cloud RPA）"

![](https://intranetproxy.alipay.com/skylark/lark/0/2021/png/278097/1621825275338-04525d70-7d5c-4684-9414-3be43bbb6f1b.png)

b. 在新的弹窗中点击"启用扩展程序"



![](https://intranetproxy.alipay.com/skylark/lark/0/2021/png/278097/1621825394863-ac40f0c0-69ce-4572-a4b1-438a059cf9eb.png)

c. 输入网址chrome://extensions/，打开扩展程序页面，可以看到RPA插件；

d. 确保插件处于启用状态。

![](https://intranetproxy.alipay.com/skylark/lark/0/2021/png/278097/1621394861128-52958e12-13c9-4280-9ae0-6a439d34b0c6.png)



### 2. 访问本地网页 

如果Chrome插件访问保存在本地磁盘的网页文件，需要开启"允许访问文件网址"

a. 点击插件的"详细信息"

b. 开启"允许访问文件网址"。

![](https://cdn.nlark.com/yuque/0/2020/png/287010/1584499918552-a489b014-62da-4e46-a6b9-a695b7faebd6.png)



### 3. 出现报错"未检测到Chrome扩展" 

输入网址chrome://extensions/，打开扩展程序页面。

**步骤1：如果已安装，先移除RPA插件，再参照步骤2安装插件；** ![](https://intranetproxy.alipay.com/skylark/lark/0/2021/png/268678/1621821005758-5db58939-0081-4e84-ab17-5a957fcc5848.png)
**步骤2：如果未安装，直接按以下步骤安装插件** 

a. 开启开发者模式（网页右上角）；![](https://cdn.nlark.com/yuque/0/2020/png/287010/1584499777747-5d479de4-8788-4119-a6e3-aad673c8afcc.png)

b. 找到插件，默认文件路径为"C:\\Program Files (x86)\\AlibabaCloudRPA\\bin\\1.13\\chrome.crx"；

c. 将chrome.crx拖入扩展程序页面；

d. 此时上方网页弹出要添加扩展程序吗？点击添加扩展程序；

![](https://intranetproxy.alipay.com/skylark/lark/0/2021/png/278097/1621407978646-5ba5a30f-c9cb-4fee-9022-b1867f619ebc.png)

e. 此时已经将插件添加至扩展程序；

![](https://intranetproxy.alipay.com/skylark/lark/0/2021/png/278097/1621408020905-30c0a8ec-1b56-48ea-bd56-47ddf6c04a4b.png)



如果按上述方法操作，RPA插件仍然不能正常工作，请联系阿里云RPA技术支持同学。
