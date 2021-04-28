NLP组件_操作样例 
===============================

本文档主要介绍阿里云RPA可视化编辑模式下，NLP组件的基础操作示例。更多NLP功能请访问[阿里云NLP基础服务](https://ai.aliyun.com/nlp?spm=5176.19720258.J_8058803260.49.e9392c4aiiguiG)

设置NLP授权信息 
------------------------------

**必要前置组件：** 无

1. 在阿里云账号上开通NLP基础服务（具体开通方式请参考[NLP基础服务](https://ai.aliyun.com/nlp?spm=5176.19720258.J_8058803260.49.e9392c4aiiguiG)），并在阿里云账号的安全信息管理处生成对应账号的AccessKey（具体生成方式请参考[阿里云AccessKey管理](https://usercenter.console.aliyun.com/#/manage/ak)），复制AccessKey和AccessKey Secret。

![NLP授权_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6916759161/p265313.png)![NLP_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7916759161/p265314.png)2. 在可视化编辑界面，新增"设置NLP授权信息"组件，在组件中填写第1步获取到的AccessKey及AccessKey Secret，点击运行后程序会，此组件会设置好对应的NLP基础服务信息，后续具体的NLP功能才能正常使用。

![NLP_3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7916759161/p265315.png)



NLP情感分析 
----------------------------

**必要前置组件：** [设置NLP授权信息](#section-59m-akb-2di)

1. 设置好NLP授权信息后，新增"NLP情感分析"组件，在待分析文本处输入需要分析语义情感色彩的文本，本例中为"你家的商品可真是太棒了！！"，为正面积极评价。

![NLP情感分析_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7916759161/p265316.png)

2. 运行后，程序会对输入的文本进行语义分析，以日志形式将NLP语义情感分析结果展现出来，效果如下图所示（输出结果"1"代表正向积极语义，"-1"代表负面消极语义）。点击左下角日志面板，可参阅运行记录信息。

![NLP_情感分析2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7916759161/p265317.png)
