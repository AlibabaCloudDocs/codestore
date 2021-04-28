OCR组件_操作样例 
===============================

本文档主要介绍阿里云RPA可视化编辑模式下，OCR组件的基础操作示例。目前OCR组件仅在专有云场景下可以使用。
**注意**

目前OCR组件仅在专有云场景下可以使用，且需要配套OCR专有云服务。

OCR文字识别 
----------------------------

**必要前置组件：** 无

1. 准备一张待进行文字识别的图片素材，本例中选用下图素材；在可视化编辑界面，新增一个"OCR文字识别"组件，在此组件中选择选择对应的本地图片，为方便展示最终效果，新增"弹出提示框"组件，将OCR识别的结果"v_otext_1"以弹窗的形式展现出来。

![OCR文字识别_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/5226759161/p264742.png)

![OCR文字识别_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/5226759161/p264756.png)



2. 运行后，程序会直接识别对应图片上的文本内容，以弹出提示框的形式，将识别到的文本内容展现出来，效果如下图所示。点击左下角日志面板，可参阅运行记录信息。

![OCR文本识别_3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6226759161/p264766.png)



OCR增值税发票识别 
-------------------------------

**必要前置组件：** 无

1. 准备一张待进行识别的发票图片素材，本例中选用下图素材（已将敏感信息打码，实际测试时请自行准备相关图片）；在可视化编辑界面，新增一个"OCR增值税发票识别"组件，在此组件中选择选择对应的本地图片，为方便展示最终效果，新增"记录日志"组件，将OCR识别的结果"v_vat_invoice_result_1"以日志的形式展现出来。

![OCR发票识别_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6226759161/p264914.png)![OCR发票识别_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6226759161/p264917.png)

2. 运行后，程序会直接识别对应图片上的增值税关键内容，以日志的形式，将识别到的内容展现在日志面板，点击左下角日志面板，可参阅运行记录信息（已将敏感信息打码）。

![OCR发票识别_3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6226759161/p264921.png)



OCR机动车统一发票识别 
---------------------------------

**必要前置组件：** 无

1. 准备一张待进行识别的图片素材，本例中选用下图素材（已将敏感信息打码，实际测试时请自行准备相关图片）；在可视化编辑界面，新增一个"OCR机动车统一发票识别"组件，在此组件中选择选择对应的本地图片，为方便展示最终效果，新增"记录日志"组件，将OCR识别的结果"v_car_invoice_1"以日志的形式展现出来。

![OCR机动车识别_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6226759161/p264953.png)![OCR机动车发票识别_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6226759161/p264958.png)

2. 运行后，程序会直接识别对应图片上的机动车发票税目关键内容，以日志的形式，将识别到的内容展现在日志面板，点击左下角日志面板，可参阅运行记录信息（已将敏感信息打码）。

![OCR机动车识别_3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6226759161/p264961.png)



OCR火车票识别 
-----------------------------

**必要前置组件：** 无

1. 准备一张待进行识别的火车票素材，本例中选用下图素材；在可视化编辑界面，新增一个"OCR火车票识别"组件，在此组件中选择选择对应的本地图片，为方便展示最终效果，新增"记录日志"组件，将OCR识别的结果"v_train_ticket_1"以日志的形式展现出来。

![OCR识别火车票_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6226759161/p264971.png)![OCR火车票识别_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6226759161/p264965.png)

2. 运行后，程序会直接识别对应图片上的火车票关键信息，以日志的形式，将识别到的内容展现在日志面板，点击左下角日志面板，可参阅运行记录信息

![OCR火车票识别_3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6226759161/p264978.png)



OCR身份证识别 
-----------------------------

**必要前置组件：** 无

1. 准备一张待进行识别的图片素材，本例中选用下图素材（已将敏感信息打码，实际测试时请自行准备相关图片）；在可视化编辑界面，新增一个"OCR身份证识别"组件，在此组件中选择选择对应的本地图片，为方便展示最终效果，新增"记录日志"组件，将OCR识别的结果"v_id_card_result_1"以日志的形式展现出来。

![OCR身份证识别_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6226759161/p264989.png)![OCR身份证识别_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7226759161/p264992.png)

2. 运行后，程序会直接识别对应图片上的身份证关键信息，以日志的形式，将识别到的内容展现在日志面板，点击左下角日志面板，可参阅运行记录信息（已将敏感信息打码）。

![OCR身份证识别_3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7226759161/p264994.png)



OCR营业执照识别 
------------------------------

**必要前置组件：** 无

1. 准备一张待进行识别的图片素材，本例中选用下图素材（已将敏感信息打码，实际测试时请自行准备相关图片）；在可视化编辑界面，新增一个"OCR营业执照识别"组件，在此组件中选择选择对应的本地图片，为方便展示最终效果，新增"记录日志"组件，将OCR识别的结果"v_business_license_result_1"以日志的形式展现出来。

![OCR营业执照_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7226759161/p265000.png)![OCR营业执照_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7226759161/p265002.png)

2. 运行后，程序会直接识别对应图片上的营业执照关键信息，以日志的形式，将识别到的内容展现在日志面板，点击左下角日志面板，可参阅运行记录信息（已将敏感信息打码）。

![OCR营业执照识别_3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7226759161/p265003.png)



OCR银行卡识别 
-----------------------------

**必要前置组件：** 无

1. 准备一张待进行识别的图片素材，本例中选用下图素材（已将敏感信息打码，实际测试时请自行准备相关图片）；在可视化编辑界面，新增一个"OCR银行卡识别"组件，在此组件中选择选择对应的本地图片，为方便展示最终效果，新增"记录日志"组件，将OCR识别的结果"v_bank_card_result_1"以日志的形式展现出来。

![OCR银行卡_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7226759161/p265011.png)![OCR银行卡_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7226759161/p265012.png)

2. 运行后，程序会直接识别对应图片上的银行卡关键信息，以日志的形式，将识别到的内容展现在日志面板，点击左下角日志面板，可参阅运行记录信息（已将敏感信息打码）。

![OCR银行卡_3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/7226759161/p265013.png)



OCR房产证识别 
-----------------------------

**必要前置组件：** 无

1. 准备一张待进行识别的图片素材，本例中选用下图素材（已将敏感信息打码，实际测试时请自行准备相关图片）；在可视化编辑界面，新增一个"OCR房产证识别"组件，在此组件中选择选择对应的本地图片，为方便展示最终效果，新增"记录日志"组件，将OCR识别的结果"v_house_cert_result_1"以日志的形式展现出来。

![OCR房产证识别_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8226759161/p265030.png)![OCR房产证_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8226759161/p265031.png)

2. 运行后，程序会直接识别对应图片上的身份证关键信息，以日志的形式，将识别到的内容展现在日志面板，点击左下角日志面板，可参阅运行记录信息（已将敏感信息打码）。

![OCR房产证_3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8226759161/p265034.png)



OCR驾驶证识别 
-----------------------------

**必要前置组件：** 无

1. 准备一张待进行识别的图片素材，本例中选用下图素材（已将敏感信息打码，实际测试时请自行准备相关图片）；在可视化编辑界面，新增一个"OCR驾驶证识别"组件，在此组件中选择选择对应的本地图片，为方便展示最终效果，新增"记录日志"组件，将OCR识别的结果"v_drivers_license_result_1"以日志的形式展现出来。

![OCR驾驶证_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8226759161/p265225.png)![OCR驾驶证_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8226759161/p265223.png)

2. 运行后，程序会直接识别对应图片上的驾驶证关键信息，以日志的形式，将识别到的内容展现在日志面板，点击左下角日志面板，可参阅运行记录信息（已将敏感信息打码）。

![OCR驾驶证_3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8226759161/p265227.png)





OCR行驶证 
---------------------------

**必要前置组件：** 无

1. 准备一张待进行识别的图片素材，本例中选用下图素材（已将敏感信息打码，实际测试时请自行准备相关图片）；在可视化编辑界面，新增一个"OCR行驶证识别"组件，在此组件中选择选择对应的本地图片，为方便展示最终效果，新增"记录日志"组件，将OCR识别的结果"v_vehicle_license_result_1"以日志的形式展现出来。

![OCR行驶证_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8226759161/p265253.png)![OCR行驶证_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8226759161/p265254.png)

2. 运行后，程序会直接识别对应图片上的行驶证关键信息，以日志的形式，将识别到的内容展现在日志面板，点击左下角日志面板，可参阅运行记录信息（已将敏感信息打码）。

![OCR行驶证_3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8226759161/p265259.png)

OCR护照识别 
----------------------------

**必要前置组件：** 无

1. 准备一张待进行识别的图片素材，本例中选用下图素材（已将敏感信息打码，实际测试时请自行准备相关图片）；在可视化编辑界面，新增一个"OCR护照识别"组件，在此组件中选择选择对应的本地图片，为方便展示最终效果，新增"记录日志"组件，将OCR识别的结果"v_passport_result_1"以日志的形式展现出来。

![OCR护照_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8226759161/p265270.png)![OCR护照_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8226759161/p265267.png)

2. 运行后，程序会直接识别对应图片上的护照关键信息，以日志的形式，将识别到的内容展现在日志面板，点击左下角日志面板，可参阅运行记录信息（已将敏感信息打码）。

![OCR护照_3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9226759161/p265272.png)



OCR不动产证识别 
------------------------------

**必要前置组件：** 无

1. 准备一张待进行识别的图片素材，本例中选用下图素材（已将敏感信息打码，实际测试时请自行准备相关图片）；在可视化编辑界面，新增一个"OCR不动产证识别"组件，在此组件中选择选择对应的本地图片，为方便展示最终效果，新增"记录日志"组件，将OCR识别的结果"v_real_estate_cert_result_1"以日志的形式展现出来。

![OCR不动产证](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9226759161/p265280.png)![OCR不动产权_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9226759161/p265275.png)

2. 运行后，程序会直接识别对应图片上的身份证关键信息，以日志的形式，将识别到的内容展现在日志面板，点击左下角日志面板，可参阅运行记录信息（已将敏感信息打码）。

![OCR不动产权证_3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9226759161/p265283.png)



OCR食品经营许可证识别 
---------------------------------

**必要前置组件：** 无

1. 准备一张待进行识别的图片素材，本例中选用下图素材（已将敏感信息打码，实际测试时请自行准备相关图片）；在可视化编辑界面，新增一个"OCR食品经营许可证识别"组件，在此组件中选择选择对应的本地图片，为方便展示最终效果，新增"记录日志"组件，将OCR识别的结果"v_food_permit_result_1"以日志的形式展现出来。

![OCR食品经营许可证_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9226759161/p265017.png)![OCR食品经营许可_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9226759161/p265021.png)

2. 运行后，程序会直接识别对应图片上的食品经营许可关键信息，以日志的形式，将识别到的内容展现在日志面板，点击左下角日志面板，可参阅运行记录信息（已将敏感信息打码）。

![OCR食品经营许可_3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9226759161/p265024.png)

