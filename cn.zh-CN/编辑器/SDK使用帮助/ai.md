ai 
=======================

本文档主要介绍编辑器组件面板中AI目录下相关组件的使用。

ml 
====================

structure_data(image_path, template_id) 
---------------------------------------------------------

**方法描述** 

结构化模板数据识别

**参数说明** 

**image_path** *\<str\>* 图片路径

**template_id** *\<str\>* 结构化模板id

**返回值说明** 

返回结构化识别结果 *\<dict\>* 

**调用样例** - rpa.ai.ml.structure_data-

    # 代码调用样例如下：
    path = r"D:\测试图片\待识别图片.jpg"
    rpa.ai.ml.structure_data(path,"xxxxxxxxxxx")







ocr 
=====================

element_text(element, element_index=1, engine='google', window=None, eliminate_spaces=False) 
--------------------------------------------------------------------------------------------------------------

**方法描述** 

在控件区域中，通过ocr获取所有文本

**参数说明** 

**element** *\<str\>* 控件名

**element_index** *\<int\>* 控件位置

**engine** *\<str\>* 引擎

可选项：

* google : 谷歌

  

* aliyun : 阿里云

  

* paddle : 飞桨

  




**eliminate_spaces** *\<bool\>* 是否去掉识别结果中的空格

**window** *\<object\>* 控件所在窗口对象

**返回值说明** 

返回识别结果 *\<str\>* 

**调用样例** - rpa.ai.ocr.element_text-

    # 注意事项：
    # 1. 使用此方法前需要先通过捕捉控件功能捕捉对应控件
    # 2. 执行时，需要确保控件所在的页面是打开状态
    # 代码调用样例如下：
    page = rpa.app.chrome.create('www.taobao.com')
    text = rpa.ai.ocr.element_text('淘宝logo-chrome',engine='paddle')







click(element, keyword, element_index=1, keyword_index=1, engine='google', button='left', offset_x=0, offset_y=0, window=None, timeout=15) 
------------------------------------------------------------------------------------------------------------------------------------------------------------

**方法描述** 

在控件区域中，通过ocr找到keyword的子区域，并对子区域的中心点为坐标，模拟鼠标点击

**参数说明** 

**element** *\<str\>* 控件名

**keyword** *\<str\>* 关键词

**element_index** *\<int\>* 控件位置

**keyword_index** *\<int\>* 关键词位置

**engine** *\<str\>* 引擎

可选项：

* google : 谷歌

  

* aliyun : 阿里云

  

* paddle : 飞桨

  




**button** *\<str\>* 鼠标键位

可选项：

* left : 左键

  

* right : 右键

  




**offset_x** *\<int\>* 横向偏移量

**offset_y** *\<int\>* 纵向偏移量

**window** *\<object\>* 控件所在窗口对象

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.ai.ocr.click-

    # 注意事项：
    # 1. 使用此方法前需要先通过捕捉控件功能捕捉对应控件
    # 2. 执行时，需要确保控件所在的页面是打开状态
    # 3. 此方法会在指定控件上，识别指定的关键词文本，以识别结果为原点，根据设定的偏移量移动鼠标，然后执行模拟点击。
    # 代码调用样例如下，本例中从页面元素上识别关键词"文档"，随后将鼠标移动到关键词上执行模拟点击动作：
    page = rpa.app.chrome.create('www.aliyun.com')
    rpa.ai.ocr.click('阿里云右上角banner-chrome','文档',engine='paddle',offset_x=0,offset_y=0)







double_click(element, keyword, element_index=1, keyword_index=1, engine='google', offset_x=0, offset_y=0, window=None, timeout=15) 
----------------------------------------------------------------------------------------------------------------------------------------------------

**方法描述** 

在控件区域中，通过ocr找到keyword的子区域，并对子区域的中心点为坐标，模拟鼠标双击

**参数说明** 

**element** *\<str\>* 控件名

**keyword** *\<str\>* 关键词

**element_index** *\<int\>* 控件位置

**keyword_index** *\<int\>* 关键词位置

**engine** *\<str\>* 引擎

可选项：

* google : 谷歌

  

* aliyun : 阿里云

  

* paddle : 飞桨

  




**offset_x** *\<int\>* 横向偏移量

**offset_y** *\<int\>* 纵向偏移量

**window** *\<object\>* 控件所在窗口对象

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.ai.ocr.double_click-

    # 注意事项：
    # 1. 使用此方法前需要先通过捕捉控件功能捕捉对应控件
    # 2. 执行时，需要确保控件所在的页面是打开状态
    # 3. 此方法会在指定控件上，识别指定的关键词文本，以识别结果为原点，根据设定的偏移量移动鼠标，然后执行模拟双击。
    # 代码调用样例如下，本例中从页面元素上识别关键词"文档"，随后将鼠标移动到关键词上执行模拟双击动作：
    page = rpa.app.chrome.create('www.aliyun.com')
    rpa.ai.ocr.double_click('阿里云右上角banner-chrome','文档',engine='paddle',offset_x=0,offset_y=0)







input_text(element, keyword, value, element_index=1, keyword_index=1, engine='google', simulate=False, offset_x=0, offset_y=0, window=None, wait_mili_seconds=20, timeout=15) 
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**方法描述** 

在控件区域中，通过ocr找到keyword的子区域，并对子区域的中心点为坐标，模拟键盘发送

**参数说明** 

**element** *\<str\>* 控件名

**keyword** *\<str\>* 关键词

**value** *\<str\>* 输入的内容

**element_index** *\<int\>* 控件位置

**keyword_index** *\<int\>* 关键词位置

**engine** *\<str\>* 引擎

可选项：

* google : 谷歌

  

* aliyun : 阿里云

  

* paddle : 飞桨

  




**offset_x** *\<int\>* 横向偏移量

**offset_y** *\<int\>* 纵向偏移量

**window** *\<object\>* 控件所在窗口对象

**wait_mili_seconds** *\<int\>* 字符间输入间隔（毫秒），仅在模拟输入下有效，默认值为20，最大值100，该值设置过大可能会引起超时

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.ai.ocr.input_text-

    # 注意事项：
    # 1. 使用此方法前需要先通过捕捉控件功能捕捉对应控件
    # 2. 执行时，需要确保控件所在的页面是打开状态
    # 3. 此方法会在指定控件上，识别指定的关键词文本，以识别结果为原点，根据设定的偏移量移动鼠标，然后模拟输入指定文本。
    # 代码调用样例如下，本例中从页面元素上识别关键词"百度"，随后将鼠标左移350个像素，然后模拟输入指定内容：
    page = rpa.app.chrome.create('www.baidu.com')
    rpa.ai.ocr.input_text('百度一下-chrome','百度','阿里云RPA',engine='paddle',offset_x=-350)







mouse_move(element, keyword, element_index=1, keyword_index=1, engine='google', offset_x=0, offset_y=0, window=None, timeout=15) 
--------------------------------------------------------------------------------------------------------------------------------------------------

**方法描述** 

在控件区域中，通过ocr找到keyword的子区域，并对子区域的中心点为坐标进行鼠标移动

**参数说明** 

**element** *\<str\>* 控件名

**keyword** *\<str\>* 关键词

**element_index** *\<int\>* 控件位置

**keyword_index** *\<int\>* 关键词位置

**engine** *\<str\>* 引擎

可选项：

* google : 谷歌

  

* aliyun : 阿里云

  

* paddle : 飞桨

  




**offset_x** *\<int\>* 横向偏移量

**offset_y** *\<int\>* 纵向偏移量

**window** *\<object\>* 控件所在窗口对象

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.ai.ocr.mouse_move-

    # 注意事项：
    # 1. 使用此方法前需要先通过捕捉控件功能捕捉对应控件
    # 2. 执行时，需要确保控件所在的页面是打开状态
    # 3. 此方法会在指定控件上，识别指定的关键词文本，以识别结果为原点，根据设定的偏移量移动鼠标。
    # 代码调用样例如下，本例中从页面元素上识别关键词"文档"，随后将鼠标移动到关键词上：
    page = rpa.app.chrome.create('www.aliyun.com')
    rpa.ai.ocr.mouse_move('阿里云右上角banner-chrome','文档',engine='paddle',offset_x=0,offset_y=0)









text(image_path, engine='aliyun', app_code='', detail=False, eliminate_spaces=False) 
------------------------------------------------------------------------------------------------------

**方法描述** 

文字识别

**参数说明** 

**image_path** *\<str\>* 图片的路径

**engine** *\<str\>* 引擎

可选项：

* google : 谷歌

  

* aliyun : 阿里云

  

* paddle : 飞桨

  




**app_code** *\<str\>* OCR文字识别appcode

**detail** *\<str\>* 是否需要识别文字的详细信息

**eliminate_spaces** *\<bool\>* 是否去掉文字识别结果中的空格(仅在detail为False时有效)

**返回值说明** 

返回识别结果 *\<str\>* 

**调用样例** - rpa.ai.ocr.text-

    # 注意事项：无
    # 代码调用样例如下：
    image_path = r'D:\2_测试文件归档\OCR文字识别.jpg'
    text = rpa.ai.ocr.text(image_path,engine='paddle')









id_card(image_path) 
-------------------------------------

**方法描述** 

身份证识别

**参数说明** 

**image_path** *\<str\>* 身份证图片路径

**返回值说明** 

返回识别结果 *\<CardFront\>* 

**调用样例** - rpa.ai.ocr.id_card-

    # 注意事项：内置SDK使用的OCR能力需要额外购买，使用前请在控制台-授权管理-AI中确认是否已授权
    # 代码调用样例如下：
    image_path = r'D:\2_测试文件归档\OCR身份证识别.png'
    id_card_data = rpa.ai.ocr.id_card(image_path)







vat_invoice(image_path, app_code='') 
------------------------------------------------------

**方法描述** 

增值发票识别

**参数说明** 

**image_path** *\<str\>* 图片路径

**app_code** *\<str\>* OCR发票识别appcode

**调用样例** - rpa.ai.ocr.vat_invoice-

    # 注意事项：
    # 1. 内置SDK使用的OCR能力需要额外购买，使用前请在控制台-授权管理-AI中确认是否已授权
    # 2. 此方法支持以输入appcode的形式调用阿里云API相关服务，appcode的获取及使用可参考：https://help.aliyun.com/document_detail/157953.html
    # 代码调用样例如下：
    image_path = r'D:\2_测试文件归档\OCR发票识别.png'
    vat_invoice_data = rpa.ai.ocr.vat_invoice(image_path,app_code='')







business_license(image_path) 
----------------------------------------------

**方法描述** 

营业执照

**参数说明** 

**image_path** *\<str\>* 营业执照图片路径

**返回值说明** 

返回识别结果 *\<json\>* 

**调用样例** - rpa.ai.ocr.business_license-

    # 注意事项：内置SDK使用的OCR能力需要额外购买，使用前请在控制台-授权管理-AI中确认是否已授权
    # 代码调用样例如下：
    image_path = r'D:\2_测试文件归档\OCR营业执照识别.png'
    business_license_data = rpa.ai.ocr.business_license(image_path)







house_cert(image_path) 
----------------------------------------

**方法描述** 

房产证

**参数说明** 

**image_path** *\<str\>* 房产证图片路径

**返回值说明** 

返回识别结果 *\<json\>* 

**调用样例** - rpa.ai.ocr.house_cert-

    # 注意事项：内置SDK使用的OCR能力需要额外购买，使用前请在控制台-授权管理-AI中确认是否已授权
    # 代码调用样例如下：
    image_path = r'D:\2_测试文件归档\OCR房产证识别.png'
    house_cert_data = rpa.ai.ocr.house_cert(image_path)







bank_card(image_path) 
---------------------------------------

**方法描述** 

银行卡

**参数说明** 

**image_path** *\<str\>* 银行卡图片路径

**返回值说明** 

返回识别结果 *\<json\>* 

**调用样例** - rpa.ai.ocr.bank_card-

    # 注意事项：内置SDK使用的OCR能力需要额外购买，使用前请在控制台-授权管理-AI中确认是否已授权
    # 代码调用样例如下：
    image_path = r'D:\2_测试文件归档\OCR银行卡.png'
    bank_card_data = rpa.ai.ocr.bank_card(image_path)







drivers_license(image_path) 
---------------------------------------------

**方法描述** 

驾驶证

**参数说明** 

**image_path** *\<str\>* 驾驶证图片路径

**返回值说明** 

返回识别结果 *\<json\>* 

**调用样例** - rpa.ai.ocr.drivers_license-

    # 注意事项：内置SDK使用的OCR能力需要额外购买，使用前请在控制台-授权管理-AI中确认是否已授权
    # 代码调用样例如下：
    image_path = r'D:\2_测试文件归档\OCR驾驶证识别.png'
    drivers_license_data = rpa.ai.ocr.drivers_license(image_path)







vehicle_license(image_path) 
---------------------------------------------

**方法描述** 

行驶证

**参数说明** 

**image_path** *\<str\>* 行驶证图片路径

**返回值说明** 

返回识别结果 *\<json\>* 

**调用样例** - rpa.ai.ocr.vehicle_license-

    # 注意事项：内置SDK使用的OCR能力需要额外购买，使用前请在控制台-授权管理-AI中确认是否已授权
    # 代码调用样例如下：
    image_path = r'D:\2_测试文件归档\OCR行驶证识别.png'
    vehicle_license_data = rpa.ai.ocr.vehicle_license(image_path)









passport(image_path) 
--------------------------------------

**方法描述** 

护照

**参数说明** 

**image_path** *\<str\>* 护照

**返回值说明** 

返回识别结果 *\<json\>* 

**调用样例** - rpa.ai.ocr.passport-

    # 注意事项：内置SDK使用的OCR能力需要额外购买，使用前请在控制台-授权管理-AI中确认是否已授权
    # 代码调用样例如下：
    image_path = r'D:\2_测试文件归档\OCR护照识别.png'
    passport_data = rpa.ai.ocr.passport(image_path)







real_estate_cert(image_path) 
----------------------------------------------

**方法描述** 

不动产证

**参数说明** 

**image_path** *\<str\>* 不动产证

**返回值说明** 

返回识别结果 *\<json\>* 

**调用样例** - rpa.ai.ocr.real_estate_cert-

    # 注意事项：内置SDK使用的OCR能力需要额外购买，使用前请在控制台-授权管理-AI中确认是否已授权
    # 代码调用样例如下：
    image_path = r'D:\2_测试文件归档\OCR不动产证识别.png'
    real_estate_cert_data = rpa.ai.ocr.real_estate_cert(image_path)









food_permit(image_path) 
-----------------------------------------

**方法描述** 

⻝品经营许可证

**参数说明** 

**image_path** *\<str\>* ⻝品经营许可证

**返回值说明** 

返回识别结果 *\<json\>* 

**调用样例** - rpa.ai.ocr.food_permit-

    # 注意事项：内置SDK使用的OCR能力需要额外购买，使用前请在控制台-授权管理-AI中确认是否已授权
    # 代码调用样例如下：
    image_path = r'D:\2_测试文件归档\OCR食品经营许可.png'
    food_permit_data = rpa.ai.ocr.food_permit(image_path)







bank_account_permit(image_path) 
-------------------------------------------------

**方法描述** 

银⾏开户许可证

**参数说明** 

**image_path** *\<str\>* 银⾏开户许可证

**返回值说明** 

返回识别结果 *\<json\>* 

**调用样例** - rpa.ai.ocr.bank_account_permit-

    # 注意事项：内置SDK使用的OCR能力需要额外购买，使用前请在控制台-授权管理-AI中确认是否已授权
    # 代码调用样例如下：
    image_path = r'D:\2_测试文件归档\OCR银行开户许可.png'
    bank_account_permit_data = rpa.ai.ocr.bank_account_permit(image_path)







car_invoice(image_path) 
-----------------------------------------

**方法描述** 

机动车发票

**参数说明** 

**image_path** *\<str\>* 机动车发票图片路径

**返回值说明** 

返回识别结果 *\<json\>* 

**调用样例** - rpa.ai.ocr.car_invoice-

    # 注意事项：内置SDK使用的OCR能力需要额外购买，使用前请在控制台-授权管理-AI中确认是否已授权
    # 代码调用样例如下：
    image_path = r'D:\2_测试文件归档\OCR机动车发票.png'
    car_invoice_data = rpa.ai.ocr.car_invoice(image_path)









train_ticket(image_path) 
------------------------------------------

**方法描述** 

火车票

**参数说明** 

**image_path** *\<str\>* 火车票图片路径

**返回值说明** 

返回识别结果 *\<json\>* 

**调用样例** - rpa.ai.ocr.train_ticket-

    # 注意事项：内置SDK使用的OCR能力需要额外购买，使用前请在控制台-授权管理-AI中确认是否已授权
    # 代码调用样例如下：
    image_path = r'D:\2_测试文件归档\OCR火车票.png'
    train_ticket_data = rpa.ai.ocr.train_ticket(image_path)









table(file_path, index=1) 
-------------------------------------------

**方法描述** 

识别表格

**参数说明** 

**file_path** *\<str\>* 图片文件名

**index** *\<str\>* 页面中的表格索引

**返回值说明** 

返回表格内容的二维数组 *\<list\>* 

**调用样例** - rpa.ai.ocr.table-

    # 注意事项：内置SDK使用的OCR能力需要额外购买，使用前请在控制台-授权管理-AI中确认是否已授权
    # 图片中存在多个表格的情况，可以设置参数Index来指定需识别的单个表格，index从1开始。
    # 代码调用样例如下：
    image_path = r'D:\2_测试文件归档\表格图片.png'
    table_data = rpa.ai.ocr.table(image_path,index=2)







tables(file_path) 
-----------------------------------

**方法描述** 

识别页面中的所有表格信息，用于页面中有多个表格的情况

**参数说明** 

**file_path** *\<str\>* 图片文件名

**返回值说明** 

返回识别结果的三维数组，数组的第一维代表页面中的表格索引，后两个维度代表表格内容 *\<object\>* 

**调用样例** - rpa.ai.ocr.tables-

    # 注意事项：内置SDK使用的OCR能力需要额外购买，使用前请在控制台-授权管理-AI中确认是否已授权
    # 返回值形如[ 表格1内容（二维列表）, 表格2内容（二维列表）]
    # 代码调用样例如下：
    image_path = r'D:\2_测试文件归档\表格图片.png'
    table_data = rpa.ai.ocr.tables(image_path)









is_key_existing(element, keyword, element_index=1, engine='google', window=None) 
--------------------------------------------------------------------------------------------------

**方法描述** 

判断OCR识别结果中是否存在关键词

**参数说明** 

**element** *\<str\>* 控件名

**keyword** *\<str\>* 关键词

**element_index** *\<int\>* 控件位置

**engine** *\<str\>* 引擎

可选项：

* google : 谷歌

  

* aliyun : 阿里云

  

* paddle : 飞桨

  




**window** *\<object\>* 控件所在窗口对象

**返回值说明** 

返回关键词是否存在于OCR识别结果中 *\<bool\>* 

**调用样例** - rpa.ai.ocr.is_key_existing-

    # 注意事项：
    # 1. 使用此方法前需要先通过捕捉控件功能捕捉对应控件
    # 2. 执行时，需要确保控件所在的页面是打开状态
    # 代码调用样例如下，本例中判断对应元素的文本识别结果中是否包括关键词"文档"：
    page = rpa.app.chrome.create('www.aliyun.com')
    flag = rpa.ai.ocr.is_key_existing('阿里云右上角banner-chrome',keyword='文档',engine='paddle')









nlp 
=====================

auth(access_key_id, access_key_secret) 
--------------------------------------------------------

**方法描述** 

授权信息,在阿里云官网，用户-\>AcessKey管理中查看

**参数说明** 

**access_key_id** *\<str\>* 访问key

**access_key_secret** *\<str\>* key对应密钥

**调用样例** - rpa.ai.nlp.auth-

    # 注意事项：使用NLP功能需要先设置AK信息。
    # 服务获取可参考阿里云NLP服务官网：https://ai.aliyun.com/nlp?spm=a2c4g.11186623.2.4.a03b70ccuJWNOS
    # 代码调用样例如下：
    ak = 'LT******X'
    ak_secret = '6a******LQ'
    rpa.ai.nlp.auth(ak ,ak_secret )







word_segment(text, language='ZH') 
---------------------------------------------------

**方法描述** 

nlp分词

**参数说明** 

**text** *\<str\>* 要分词的文本

**language** *\<str\>* 要处理的语言，默认ZH

可选项：

* ZH : 中文中粒度

  

* ZH_Big : 中文大粒度

  

* ZH_Small : 中文小粒度

  

* EN : 英文

  

* TH : 泰语

  




**返回值说明** 

返回分词结果的list，如\[word1,word2,...\] *\<list\>* 

**调用样例** - rpa.ai.nlp.word_segment-

    # 注意事项：使用NLP功能需要先设置AK信息。
    # 服务获取可参考阿里云NLP服务官网：https://ai.aliyun.com/nlp?spm=a2c4g.11186623.2.4.a03b70ccuJWNOS
    # 代码调用样例如下：
    ak = 'LT******X'
    ak_secret = '6a******LQ'
    rpa.ai.nlp.auth(ak ,ak_secret )
    text="阿里云RPA，助力流程自动化，引领企业智能"
    word_list = rpa.ai.nlp.word_segment(text)







word_pos(text) 
--------------------------------

**方法描述** 

nlp词性标注

**参数说明** 

**text** *\<str\>* 要处理的文本

**返回值说明** 

返回字典的list，如list\[dict1,dict2,...\]，每个dict包含{"pos":词性, "word":词} *\<list\>* 

**调用样例** - rpa.ai.nlp.word_pos-

    # 注意事项：使用NLP功能需要先设置AK信息。
    # 服务获取可参考阿里云NLP服务官网：https://ai.aliyun.com/nlp?spm=a2c4g.11186623.2.4.a03b70ccuJWNOS
    # 词性标注含义可参考：https://help.aliyun.com/document_detail/61378.html
    # 代码调用样例如下：
    ak = 'LT******X'
    ak_secret = '6a******LQ'
    rpa.ai.nlp.auth(ak ,ak_secret )
    text="阿里云RPA，助力流程自动化，引领企业智能"
    word_pos = rpa.ai.nlp.word_pos(text)







entity(text, output_type='simple') 
----------------------------------------------------

**方法描述** 

nlp命名实体

**参数说明** 

**text** *\<str\>* 要处理的文本

**output_type** *\<str\>* 控制输出样式，其值可为"simple"或者"full"，分别表示简单输出和详细输出，简单输出包括实体和标签，详细输出包括实体、标签、权重和近义词。

**返回值说明** 

返回字典的list，如list\[dict1,dict2,...\]，每个dict包含{"synonym":词性, "weight":权重（重要性），"word":词，"tag":类别} *\<list\>* 

**调用样例** - rpa.ai.nlp.entity-

    # 注意事项：使用NLP功能需要先设置AK信息。
    # 服务获取可参考阿里云NLP服务官网：https://ai.aliyun.com/nlp?spm=a2c4g.11186623.2.4.a03b70ccuJWNOS
    # 实体标注可参考：https://help.aliyun.com/document_detail/61387.html
    # 代码调用样例如下：
    ak = 'LT******X'
    ak_secret = '6a******LQ'
    rpa.ai.nlp.auth(ak ,ak_secret )
    text="阿里云RPA，助力流程自动化，引领企业智能"
    entity= rpa.ai.nlp.entity(text)







sentiment(text) 
---------------------------------

**方法描述** 

nlp情感分析

**参数说明** 

**text** *\<str\>* 要处理的文本

**返回值说明** 

返回情感度量的int值 *\<int\>* 

**调用样例** - rpa.ai.nlp.sentiment-

    # 注意事项：使用NLP功能需要先设置AK信息。
    # 服务获取可参考阿里云NLP服务官网：https://ai.aliyun.com/nlp?spm=a2c4g.11186623.2.4.a03b70ccuJWNOS
    # 代码调用样例如下：
    ak = 'LT******X'
    ak_secret = '6a******LQ'
    rpa.ai.nlp.auth(ak ,ak_secret )
    text="阿里云RPA，助力流程自动化，引领企业智能"
    sentiment= rpa.ai.nlp.sentiment(text)







head_word_extraction(text, language='ZH') 
-----------------------------------------------------------

**方法描述** 

nlp中心词提取

**参数说明** 

**text** *\<str\>* 要处理的文本

**language** *\<str\>* 文本的语言, 目前仅支持 ZH(中文)

**返回值说明** 

返回中心词的list *\<list\>* 

**调用样例** - rpa.ai.nlp.head_word_extraction-

    # 注意事项：使用NLP功能需要先设置AK信息。
    # 服务获取可参考阿里云NLP服务官网：https://ai.aliyun.com/nlp?spm=a2c4g.11186623.2.4.a03b70ccuJWNOS
    # 代码调用样例如下：
    ak = 'LT******X'
    ak_secret = '6a******LQ'
    rpa.ai.nlp.auth(ak ,ak_secret )
    text="阿里云RPA，助力流程自动化，引领企业智能"
    key_word_list = rpa.ai.nlp.head_word_extraction(text)









text_structure(text, type_flag=True, domain='ecommerce') 
--------------------------------------------------------------------------

**方法描述** 

nlp智能文本分类

**参数说明** 

**text** *\<str\>* 要处理的文本

**type_flag** *\<bool\>* 是否需要关键词抽取功能

**domain** *\<str\>* 领域模型选择

可选项：

* ecommerce : 电商领域

  

* news : 新闻领域

  




**返回值说明** 

返回分类结果的字典，字典结构为 dict{"tags":文本的关键词以及其对应属性,"label_name":文本的分类结果} *\<dict\>* 

**example-rpa.ai.nlp.text_structure-** 



text_extraction(text, language='ZH') 
------------------------------------------------------

**方法描述** 

nlp文本信息抽取

**参数说明** 

**text** *\<str\>* 要处理的文本

**language** *\<str\>* 文本的语言，目前仅支持中文 ZH

**返回值说明** 

返回文本信息抽取结果的字典 *\<dict\>* 

**调用样例** - rpa.ai.nlp.text_extraction-

    # 注意事项：使用NLP功能需要先设置AK信息。
    # 服务获取可参考阿里云NLP服务官网：https://ai.aliyun.com/nlp?spm=a2c4g.11186623.2.4.a03b70ccuJWNOS
    # 代码调用样例如下：
    ak = 'LT******X'
    ak_secret = '6a******LQ'
    rpa.ai.nlp.auth(ak ,ak_secret )
    text="""
        流程自动化合同
        甲方：企业
        乙方：小明，收款账户为6666888866668888
        """
    text_extraction_dict = rpa.ai.nlp.text_extraction(text)







