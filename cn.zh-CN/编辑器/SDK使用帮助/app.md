app 
========================

本文档主要介绍编辑器组件面板中App Integration目录下相关组件的使用。

ie 
====================

create(url, wait=True, visible=True, timeout=100) 
-------------------------------------------------------------------

**方法描述** 

创建ie对象

**参数说明** 

**url** *\<str\>* 要打开的url

**wait** *\<bool\>* 是否等待加载完成 默认True

**visible** *\<bool\>* 是否可见 默认True

可选项：

* timeout : 等待网页加载的超时时间，默认100秒

  




**返回值说明** 

返回IETab对象 *\<IETab\>* 

**调用样例** - rpa.app.ie.create-

    # 注意事项：无
    # 代码调用样例如下：
    page = rpa.app.ie.create('www.baidu.com')









catch_host(wnd) 
---------------------------------

**方法描述** 

捕获嵌入式的IE窗口

**返回值说明** 

返回IETab对象 *\<IETab\>* 

**调用样例** - rpa.app.ie.catch_host-

    # 注意事项：此方法针对windows应用内嵌的ie页面，需先使用win32.catch方法获取应用窗口对象。
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch('网店云管家',mode='substr')
    page = rpa.app.ie.catch_host(wnd)







catch(name, mode='title', pattern='contain', timeout=10) 
--------------------------------------------------------------------------

**方法描述** 

捕获已打开的页面

**参数说明** 

**name** *\<str\>* 标题或者url

**mode** *\<str\>* 页面匹配类型

可选项：

* title : 标题

  

* url : url

  




**pattern** *\<str\>* 页面匹配模式

可选项：

* equal : 完全匹配

  

* contain : 包含匹配

  

* regular : 正则表达式匹配

  




**返回值说明** 

返回IETab对象 *\<IETab\>* 

**调用样例** - rpa.app.ie.catch-

    # 注意事项：使用此方法前需确认已打开对应IE网页
    # 代码调用样例如下：
    page = rpa.app.ie.catch('淘宝网 - 淘！我喜欢', mode='title', pattern='equal')







catch_specific_pages(name, mode='title', pattern='contain') 
-----------------------------------------------------------------------------

**方法描述** 

捕获满足条件的所有页面

**参数说明** 

**name** *\<str\>* 标题或者url

**mode** *\<str\>* 页面匹配类型

可选项：

* title : 标题

  

* url : url

  




**pattern** *\<str\>* 页面匹配模式

可选项：

* equal : 完全匹配

  

* contain : 包含匹配

  

* regular : 正则表达式匹配

  




**返回值说明** 

返回IETab对象的列表 *\<list\>* 

**调用样例** - rpa.app.ie.catch_specific_pages-

    # 注意事项：使用此方法前需确认至少已打开一个符合条件的网页
    # 代码调用样例如下：
    page_list = rpa.app.ie.catch_specific_pages('阿里云')







catch_all_pages() 
-----------------------------------

**方法描述** 

返回所有的页面

**调用样例** - rpa.app.ie.catch_all_pages-

    # 注意事项：无
    # 代码调用样例如下：
    page_list = rpa.app.ie.catch_all_pages()







close_all() 
-----------------------------

**方法描述** 

关闭所有的页面

**调用样例** - rpa.app.ie.close_all-

    # 注意事项：无
    # 代码调用样例如下：
    rpa.app.ie.close_all()







close() 
-------------------------

**方法描述** 

关闭浏览器对象

**调用样例** - rpa.app.ie.IETab.close-

    # 注意事项：此方法仅能基于IETab实例对象进行操作
    # 代码调用样例如下：
    page = rpa.app.ie.create('www.taobao.com')
    page.close()









navigate(url, wait=True, timeout=100) 
-------------------------------------------------------

**方法描述** 

跳转到指定链接

**参数说明** 

**url** *\<str\>* 要打开的url

**wait** *\<bool\>* 是否等待加载完成

**timeout** *\<int\>* 等待超时时间, 默认100s

**调用样例** - rpa.app.ie.IETab.navigate-

    # 注意事项：此方法仅能基于IETab实例对象进行操作
    # 代码调用样例如下：
    page = rpa.app.ie.create('www.taobao.com')
    page.navigate('www.aliyun.com')







back(wait=True, timeout=100) 
----------------------------------------------

**方法描述** 

浏览器后退

**参数说明** 

**wait** *\<bool\>* 是否等待加载完成

**timeout** *\<int\>* 等待超时时间, 默认100s

**调用样例** - rpa.app.ie.IETab.back-

    # 注意事项：此方法仅能基于IETab实例对象进行操作
    # 代码调用样例如下：
    page = rpa.app.ie.create('www.taobao.com')
    page.navigate('www.aliyun.com')
    page.back()







forward(wait=True, timeout=100) 
-------------------------------------------------

**方法描述** 

浏览器前进

**参数说明** 

**wait** *\<bool\>* 是否等待加载完成

**timeout** *\<int\>* 等待超时时间, 默认100s

**调用样例** - rpa.app.ie.IETab.forward-

    # 注意事项：此方法仅能基于IETab实例对象进行操作
    # 代码调用样例如下：
    page = rpa.app.ie.create('www.taobao.com')
    page.navigate('www.aliyun.com')
    page.back()
    page.forward()







get_cookies() 
-------------------------------

**方法描述** 

获取cookie

**返回值说明** 

返回cookie *\<list\>* 

**调用样例** - rpa.app.ie.IETab.get_cookies-

    # 注意事项：此方法仅能基于IETab实例对象进行操作
    # 代码调用样例如下：
    page = rpa.app.ie.create('www.taobao.com')
    cookies = page.get_cookies()







wait_loaded(element, index=1, parent_element=None, timeout=10, ignore_error=True) 
---------------------------------------------------------------------------------------------------

**方法描述** 

控件加载

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**timeout** *\<int\>* 超时时间

**parent_element** *\<Element\>* 父控件对象

**ignore_error** *\<bool\>* 忽略错误

**调用样例** - rpa.app.ie.IETab.wait_loaded-

    # 注意事项：此方法仅能基于IETab实例对象进行操作，使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    page = rpa.app.ie.create('www.taobao.com')
    flag = page.wait_loaded('淘宝logo')







wait_disappear(element, index=1, parent_element=None, timeout=10) 
-----------------------------------------------------------------------------------

**方法描述** 

等待控件消失

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**timeout** *\<int\>* 超时时间

**parent_element** *\<Element\>* 父控件对象

**调用样例** - rpa.app.ie.IETab.wait_disappear-

    # 注意事项：此方法仅能基于IETab实例对象进行操作，超过预定时间控件仍未消失则抛出异常
    # 代码调用样例如下：
    page = rpa.app.ie.create('www.taobao.com')
    flag = page.wait_disappear('淘宝logo')









download_by_url(url, path, wait=True, complete_timeout=120) 
-----------------------------------------------------------------------------

**方法描述** 

根据url下载文件

**参数说明** 

**url** *\<str\>* 下载文件的链接

**path** *\<str\>* 保存的文件路径

**complete_timeout** *\<int\>* 超时时间

**wait** *\<bool\>* 是否等待完成

**调用样例** - rpa.app.ie.IETab.download_by_url-

    # 注意事项：此方法仅能基于IETab实例对象进行操作
    # 代码调用样例如下，运行后会下载对应文件到指定路径：
    page = rpa.app.ie.create('www.cninfo.com.cn')
    download_url = 'www.cninfo.com.cn/new/announcement/download?bulletinId=1209275224&announceTime=2021-02-10'
    download_path = r'D:\阿里巴巴-SW.pdf'
    page.download_by_url(download_url,download_path)







download_by_element(path, element, index=1, parent_element=None, wait=True, complete_timeout=120) 
-------------------------------------------------------------------------------------------------------------------

**方法描述** 

根据控件下载文件

**参数说明** 

**path** *\<str\>* 保存的文件路径

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**complete_timeout** *\<int\>* 超时时间

**wait** *\<bool\>* 是否等待完成

**调用样例** - rpa.app.ie.IETab.download_by_element-

    # 注意事项：此方法仅能基于IETab实例对象进行操作，使用前需要先通过捕捉控件功能获取页面上的下载按钮并验证可用
    # 代码调用样例如下，运行后会下载对应文件到指定路径：
    url = 'http://www.cninfo.com.cn/new/disclosure/detail?plate=hke&orgId=9900042435&stockCode=09988&announcementId=1209275224'
    page = rpa.app.ie.create(url)
    download_path = r'D:\阿里巴巴-SW-公开资料.pdf'
    page.download_by_element(download_path,'公告下载-ie')







upload(element, file, index=1, parent_element=None, timeout=10) 
---------------------------------------------------------------------------------

**方法描述** 

上传文件

**参数说明** 

**file** *\<str\>* 上传的文件路径

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.app.ie.IETab.upload-

    # 注意事项：此方法仅能基于IETab实例对象进行操作，使用前需要先通过捕捉控件功能获取页面上的上传按钮并验证可用
    # 代码调用样例如下，最终会产生XX结果(即对示例代码做简要描述)
    url = 'https://duguang.aliyun.com/experience?type=standard&subtype=idcard#intro'
    page = rpa.app.ie.create(url)
    upload_path = r'D:\2_测试文件归档\OCR身份证识别.jpg'
    page.upload('上传图片-ie',upload_path)







execute_js(code, timeout=10) 
----------------------------------------------

**方法描述** 

执行js代码

**参数说明** 

**code** *\<str\>* js代码

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.app.ie.IETab.execute_js-

    # 注意事项：此方法仅能基于IETab实例对象进行操作，如果需要在js中获取返回值，请使用js标准的function写法。
    # 代码调用样例如下，需要先创建一个IETab对象，将在此页面对象上执行对应js脚本：
    page = rpa.app.ie.create('www.baidu.com')
    js_code = """
    function test(){ 
        var div1 = document.getElementById("su");
        return(div1) 
        } ; 
    result = test() ; 
    console.log(result) ; 
    alert(result)
    """
    page.execute_js(js_code)









table(element, return_type='text', index=1, parent_element=None, timeout=10) 
----------------------------------------------------------------------------------------------

**方法描述** 

获取表格

**参数说明** 

**return_type** *\<str\>* 返回类型

可选项：

* text : 文本类型

  

* html : html类型

  




**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 超时时间

**返回值说明** 

返回二维数组或html *\<list\>* 

**调用样例** - rpa.app.ie.IETab.table-

    # 注意事项：此方法仅能基于IETab实例对象进行操作，使用前需要先通过捕捉控件功能捕捉页面上的标准表格元素（html标签为table的）
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.ie.create(url)
    table_data = page.table('表格-ie')







scroll(height, element=None, index=1, parent_element=None, timeout=10, direction='top') 
---------------------------------------------------------------------------------------------------------

**方法描述** 

滚动页面(传入控件则为设置控件内的滚动条)

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 超时时间

**height** *\<int\>* 设置则滚动指定高度

**direction** *\<str\>* 选择滚动条方向

可选项：

* left : 向左滚动

  

* top : 向下滚动

  




**返回值说明** 

返回True表示还能滚动，返回False表示已经滚到底 *\<bool\>* 

**调用样例** - rpa.app.ie.IETab.scroll-

    # 注意事项：此方法仅能基于IETab实例对象进行操作
    # 代码调用样例如下，运行后，会在打开的网页中将滑块向下滑动500个像素：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.ie.create(url)
    page.scroll(500)









scroll_into_view(element, index=1, parent_element=None, timeout=10) 
-------------------------------------------------------------------------------------

**方法描述** 

滚动控件到可视区域

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.app.ie.IETab.scroll_into_view-

    # 注意事项：此方法仅能基于IETab实例对象进行操作，使用前需要先使用捕捉控件功能获取页面元素
    # 代码调用样例如下，运行后会在打开的网页中，将滑块向下滑动，直到指定的页面元素处于可见范围内：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.ie.create(url)
    page.scroll_into_view('网页底部-ie')







get_scroll_height(element=None, index=1, parent_element=None, timeout=10) 
-------------------------------------------------------------------------------------------

**方法描述** 

获取纵向滚动条高度(传入控件则为设置控件内的滚动条)

**参数说明** 

**element** *\<str\>* 控件

**返回值说明** 

返回纵向滚动条高度 *\<str\>* 

**调用样例** - rpa.app.ie.IETab.get_scroll_height-

    # 注意事项：此方法仅能基于IETab实例对象进行操作
    # 代码调用样例如下，运行后会获取对应网页纵向滑块当前的位置：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.ie.create(url)
    height = page.get_scroll_height()







get_scroll_width(element=None, index=1, parent_element=None, timeout=10) 
------------------------------------------------------------------------------------------

**方法描述** 

获取横向滚动宽度(传入控件则为设置控件内的滚动条)

**参数说明** 

**element** *\<str\>* 控件

**返回值说明** 

返回横向滚动宽度 *\<str\>* 

**调用样例** - rpa.app.ie.IETab.get_scroll_width-

    # 注意事项：此方法仅能基于IETab实例对象进行操作
    # 代码调用样例如下，运行后会获取对应网页横向滑块当前的位置：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.ie.create(url)
    height = page.get_scroll_width()









text(element=None, index=1, parent_element=None, timeout=10) 
------------------------------------------------------------------------------

**方法描述** 

获取文本

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 超时时间

**返回值说明** 

返回文本，不传控件返回浏览器上所有的文本 *\<str\>* 

**调用样例** - rpa.app.ie.IETab.text-

    # 注意事项：此方法仅能基于IETab实例对象进行操作，如果要获取指定元素的文本，使用前需要先使用捕捉控件功能获取页面元素
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.ie.create(url)
    text = page.text(element='网页底部-ie')







html(element=None, index=1, parent_element=None, timeout=10) 
------------------------------------------------------------------------------

**方法描述** 

获取html

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 超时时间

**返回值说明** 

返回html，不传控件返回浏览器上所有的html *\<str\>* 

**调用样例** - rpa.app.ie.IETab.html-

    # 注意事项：此方法仅能基于IETab实例对象进行操作，如果要获取指定元素的html，使用前需要先使用捕捉控件功能获取页面元素
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.ie.create(url)
    html = page.html('网页底部-ie')







input_text(element, value, index=1, parent_element=None, simulate=True, replace=True, sent_raw=False, wait_mili_seconds=20, timeout=10) 
---------------------------------------------------------------------------------------------------------------------------------------------------------

**方法描述** 

输入文本

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**value** *\<str\>* 输入的内容

**parent_element** *\<Element\>* 父控件对象

**simulate** *\<bool\>* 是否模拟输入

**replace** *\<bool\>* 是否清空之前的内容

**sent_raw** *\<bool\>* 是否发送原始按键，仅非模拟模式有效

**wait_mili_seconds** *\<int\>* 字符间输入间隔（毫秒），仅在模拟输入下有效，默认值为20，最大值100，该值设置过大可能会引起超时

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.app.ie.IETab.input_text-

    # 注意事项：此方法仅能基于IETab实例对象进行操作，使用前需要先通过捕捉控件功能获取页面输入框元素
    # 代码调用样例如下：
    url = 'www.taobao.com'
    page = rpa.app.ie.create(url)
    page.input_text('淘宝搜索框-ie','RPA')







input_hotkeys(element, value, index=1, parent_element=None, timeout=10) 
-----------------------------------------------------------------------------------------

**方法描述** 

输入快捷键

**参数说明** 

**element** *\<str\>* 控件

**value** *\<str\>* 输入的内容

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.app.ie.IETab.input_hotkeys-

    # 注意事项：此方法仅能基于IETab实例对象进行操作，虚拟键写法请参考：https://www.yuque.com/aliyun_rpa/quzm63/vk
    # 代码调用样例如下：
    url = 'www.taobao.com'
    page = rpa.app.ie.create(url)
    page.input_text('淘宝搜索框-ie','RPA')
    page.input_hotkeys('淘宝搜索框-ie','VK_RETURN')







value(element, index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------

**方法描述** 

获取值

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 超时时间

**返回值说明** 

返回值 *\<str\>* 

**调用样例** - rpa.app.ie.IETab.value-

    # 注意事项：此方法仅能基于IETab实例对象进行操作，使用前需要先通过捕捉控件功能获取页面元素
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.ie.create(url)
    value = page.value('网页底部-ie')







option(element, text, type='match', index=1, parent_element=None, clear_selected=False, timeout=10) 
---------------------------------------------------------------------------------------------------------------------

**方法描述** 

通过文本下拉框选择

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**text** *\<str\>* 选择内容

**parent_element** *\<Element\>* 父控件对象

**type** *\<str\>* 匹配类型

可选项：

* match : 模糊匹配

  

* full : 完全匹配

  

* regex : 正则匹配

  




**clear_selected** *\<bool\>* 是否清空之前的选择(仅作用于多选时)

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.app.ie.IETab.option-

    # 注意事项：
    # 1.此方法仅能基于IETab实例对象进行操作，使用前需要先通过捕捉控件功能获取页面标准下拉框元素(html标签为select)
    # 2.需确认下拉框中存在对应的文本选项
    # 代码调用样例如下：
    url = 'https://kyfw.12306.cn/otn/leftTicket/init'
    page = rpa.app.ie.create(url)
    
    page.option('下拉框-ie','00:00--06:00')







option_by_index(element, item_index, index=1, parent_element=None, clear_selected=False, timeout=10) 
----------------------------------------------------------------------------------------------------------------------

**方法描述** 

通过下标下拉框选择

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**item_index** *\<int\>* 选项下标

**parent_element** *\<Element\>* 父控件对象

**clear_selected** *\<bool\>* 是否清空之前的选择(仅作用于多选时)

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.app.ie.IETab.option_by_index-

    # 注意事项：
    # 1.此方法仅能基于IETab实例对象进行操作，使用前需要先通过捕捉控件功能获取页面标准下拉框元素(html标签为select)
    # 2.需确认下拉框中选项个数，索引从1计算，不能超过选项最大个数
    # 代码调用样例如下：
    url = 'https://kyfw.12306.cn/otn/leftTicket/init'
    page = rpa.app.ie.create(url)
    
    page.option_by_index('下拉框-ie',4)







get_options(element, mode='all', index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------------------------

**方法描述** 

返回下拉框选中的值/所有的选项

**参数说明** 

**element** *\<str\>* 控件

**mode** *\<str\>* 返回类型

可选项：

* selected : 选中项

  

* all : 所有项

  




**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 超时时间

**返回值说明** 

返回列表 *\<list\>* 

**调用样例** - rpa.app.ie.IETab.get_options-

    # 注意事项：此方法仅能基于IETab实例对象进行操作，使用前需要先通过捕捉控件功能获取页面标准下拉框元素(html标签为select)
    # 代码调用样例如下：
    url = 'https://kyfw.12306.cn/otn/leftTicket/init'
    page = rpa.app.ie.create(url)
    options = page.get_options('下拉框-ie')







get_checked_state(element, index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------------------

**方法描述** 

获取勾选状态

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 超时时间

**返回值说明** 

返回勾选状态 *\<bool\>* 

**调用样例** - rpa.app.ie.IETab.get_checked_state-

    # 注意事项：此方法仅能基于IETab实例对象进行操作，使用前需要先通过捕捉控件功能获取页面上的勾选框元素
    # 代码调用样例如下：
    url = 'https://kyfw.12306.cn/otn/leftTicket/init'
    page = rpa.app.ie.create(url)
    check_state = page.get_checked_state('复选框-ie')







set_checked_state(element, value=True, index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------------------------------

**方法描述** 

勾选框操作

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**value** *\<bool\>* 传入True则勾选，传入False取消勾选

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.app.ie.IETab.set_checked_state-

    # 注意事项：此方法仅能基于IETab实例对象进行操作，使用前需要先通过捕捉控件功能获取页面上的勾选框元素
    # 代码调用样例如下：
    url = 'https://kyfw.12306.cn/otn/leftTicket/init'
    page = rpa.app.ie.create(url)
    page.set_checked_state('复选框-ie')







click(element, index=1, parent_element=None, simulate=True, button='left', timeout=10) 
--------------------------------------------------------------------------------------------------------

**方法描述** 

点击

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**simulate** *\<bool\>* 是否模拟点击

**button** *\<str\>* 鼠标键位

可选项：

* left : 左键

  

* right : 右键

  




**timeout** *\<int\>* 超时时间

**调用样例** - rpa.app.ie.IETab.click-

    # 注意事项：
    # 1. 此方法仅能基于IETab实例对象进行操作，使用前需要通过捕捉控件功能获取页面上的可点击元素
    # 2. simulate=True，即模拟点击情况下，需要对应的页面元素在可见区域，模拟鼠标点击
    # 3. simulate=False，即在非模拟点击情况下，将直接向元素发送对应点击指令
    # 代码调用样例如下：
    url = 'www.aliyun.com'
    page = rpa.app.ie.create(url)
    page.click('登录按钮-ie')







double_click(element, index=1, parent_element=None, simulate=True, timeout=10) 
------------------------------------------------------------------------------------------------

**方法描述** 

双击

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**simulate** *\<bool\>* 是否模拟点击

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.app.ie.IETab.double_click-

    # 注意事项：
    # 1. 此方法仅能基于IETab实例对象进行操作，使用前需要通过捕捉控件功能获取页面上的可点击元素
    # 2. simulate=True，即模拟点击情况下，需要对应的页面元素在可见区域，模拟鼠标点击
    # 3. simulate=False，即在非模拟点击情况下，将直接向元素发送对应点击指令
    # 代码调用样例如下：
    url = 'www.aliyun.com'
    page = rpa.app.ie.create(url)
    page.double_click('登录按钮-ie')







count(element, parent_element=None) 
-----------------------------------------------------

**方法描述** 

获取控件个数

**参数说明** 

**element** *\<str\>* 控件

**parent_element** *\<Element\>* 父控件对象

**返回值说明** 

返回个数 *\<int\>* 

**调用样例** - rpa.app.ie.IETab.count-

    # 注意事项：此方法仅能基于IETab实例对象进行操作，使用前需要通过捕捉控件功能获取页面上的元素
    # 通过捕捉相似控件功能获取相似控件元素后，常使用此方法统计控件数量
    # 代码调用样例如下：
    url = 'www.aliyun.com'
    page = rpa.app.ie.create(url)
    page.count('登录按钮-ie')







href(element, index=1, parent_element=None, timeout=10) 
-------------------------------------------------------------------------

**方法描述** 

获取链接

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 超时时间

**返回值说明** 

返回链接 *\<str\>* 

**调用样例** - rpa.app.ie.IETab.href-

    # 注意事项：此方法仅能基于IETab实例对象进行操作，使用前需要通过捕捉控件功能获取页面上附带href属性的元素
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.ie.create(url)
    link = page.href('登录按钮-ie')







process_alert(option='ok', element=None, simulate=True, index=1, parent_element=None, timeout=10) 
-------------------------------------------------------------------------------------------------------------------

**方法描述** 

弹出框点击

**参数说明** 

**option** *\<str\>* 弹出框处理

可选项：

* ok : 点击确定

  

* cancel : 点击取消

  




**element** *\<str\>* 控件(不传控件则为浏览器内的弹出框点击)

**simulate** *\<bool\>* 是否模拟

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.app.ie.IETab.process_alert-

    # 注意事项：
    # 1. 此方法仅能基于IETab实例对象进行操作
    # 2. 此方法仅能处理confirm或alert弹窗
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.ie.create(url)
    page.execute_js('alert("提示框")')
    page.process_alert()







process_prompt(text, option='ok', element=None, simulate=True, index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------------------------------------------------------

**方法描述** 

输入框输入并点击

**参数说明** 

**text** *\<str\>* 输入内容

**option** *\<str\>* 弹出框处理

可选项：

* ok : 点击确定

  

* cancel : 点击取消

  




**element** *\<str\>* 控件(不传控件则为浏览器内的弹出框点击)

**simulate** *\<bool\>* 是否模拟

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.app.ie.IETab.process_prompt-

    # 注意事项：
    # 1. 此方法仅能基于IETab实例对象进行操作
    # 2. 此方法仅能处理prompt弹窗
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.ie.create(url)
    page.execute_js('prompt("请输入内容：","")')
    page.process_prompt('RPA_TEST')







alert_message() 
---------------------------------

**方法描述** 

获取弹出框消息

**返回值说明** 

返回弹出框消息 *\<str\>* 

**调用样例** - rpa.app.ie.IETab.alert_message-

    # 注意事项：
    # 1. 此方法仅能基于IETab实例对象进行操作
    # 2. 此方法仅能处理prompt弹窗
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.ie.create(url)
    page.execute_js('alert("阿里云RPA_TEST")')
    message = page.alert_message()







pos(element, index=1, parent_element=None, timeout=10) 
------------------------------------------------------------------------

**方法描述** 

获取控件坐标

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 超时时间

**返回值说明** 

返回坐标 *\<dict\>* 

**调用样例** - rpa.app.ie.IETab.pos-

    # 注意事项：
    # 1. 此方法仅能基于IETab实例对象进行操作，使用前需要通过捕捉控件功能获取页面上的元素
    # 2. 此方法返回的坐标是以屏幕左上角为原点，页面元素的坐标------即移动网页窗口，此坐标会变化
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.ie.create(url)
    pos = page.pos('登录按钮-ie')









screenshot(element, file, index=1, parent_element=None, timeout=10) 
-------------------------------------------------------------------------------------

**方法描述** 

截图

**参数说明** 

**element** *\<str\>* 控件

**file** *\<str\>* 保存的截图路径

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.app.ie.IETab.screenshot-

    # 注意事项：
    # 1. 此方法仅能基于IETab实例对象进行操作，使用前需要通过捕捉控件功能获取页面上的元素
    # 2. 此方法会自动滚动滑块，将要操作的元素滚动到可见区域
    # 代码调用样例如下，运行后程序会对页面元素进行截图并将截图保存在指定路径：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.ie.create(url)
    save_path = r'D:\阿里云底部文本截图.jpg'
    page.screenshot('网页底部-ie',save_path)









mouse_move(element, index=1, parent_element=None, timeout=10) 
-------------------------------------------------------------------------------

**方法描述** 

鼠标移入

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.app.ie.IETab.mouse_move-

    # 注意事项：
    # 1. 此方法仅能基于IETab实例对象进行操作，使用前需要通过捕捉控件功能获取页面上的元素
    # 2. 此方法会自动滚动滑块，将要操作的元素滚动到可见区域
    # 代码调用样例如下，运行后程序会将鼠标移动到对应元素上
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.ie.create(url)
    page.mouse_move('网页底部-ie')







drag(element, x=0, y=0, index=1, parent_element=None, timeout=10) 
-----------------------------------------------------------------------------------

**方法描述** 

将控件拖拽到指定的位置

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 超时时间

**x** *\<int\>* x轴偏移量

**y** *\<int\>* y轴偏移量

**调用样例** - rpa.app.ie.IETab.drag-

    # 注意事项：此方法仅能基于IETab实例对象进行操作，使用前需要通过捕捉控件功能获取页面上的元素
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.ie.create(url)
    page.drag('登录按钮-ie',x=-500,y=100)









get_element_by_name(element, index=1, parent_element=None, timeout=10) 
----------------------------------------------------------------------------------------

**方法描述** 

获取对象

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 超时时间

**返回值说明** 

返回控件对象 *\<Element\>* 

**调用样例** - rpa.app.ie.IETab.get_element_by_name-

    # 注意事项：此方法仅能基于IETab实例对象进行操作，使用前需要通过捕捉控件功能获取页面上的元素
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.ie.create(url)
    element = page.get_element_by_name('登录按钮-ie')
    text = element.text()







get_element_by_css(css, index=1, parent_element=None, timeout=10) 
-----------------------------------------------------------------------------------

**方法描述** 

根据CSS表达式获取控件

**参数说明** 

**css** *\<str\>* CSS表达式

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 超时时间

**返回值说明** 

返回控件对象 *\<Element\>* 

**调用样例** - rpa.app.ie.IETab.get_element_by_css-

    # 注意事项：
    # 1. 此方法仅能基于IETab实例对象进行操作
    # 2. 此方法使用css选择器定位要操作的元素，请使用标准的css-selector表达式
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.ie.create(url)
    css_selector = "span.menu-title-text"
    element = page.get_element_by_css(css_selector)
    text = element.text()









url() 
-----------------------

**方法描述** 

获取url

**返回值说明** 

返回url *\<str\>* 

**调用样例** - rpa.app.ie.IETab.url-

    # 注意事项：此方法仅能基于IETab实例对象进行操作
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.ie.create(url)
    get_url = page.url()







title() 
-------------------------

**方法描述** 

获取title

**返回值说明** 

返回标题 *\<str\>* 

**调用样例** - rpa.app.ie.IETab.title-

    # 注意事项：此方法仅能基于IETab实例对象进行操作
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.ie.create(url)
    title= page.title()









reload(wait=True, timeout=100) 
------------------------------------------------

**方法描述** 

刷新页面

**参数说明** 

**wait** *\<bool\>* 是否等待加载完成

**timeout** *\<int\>* 等待超时时间, 默认100s

**调用样例** - rpa.app.ie.IETab.reload-

    # 注意事项：此方法仅能基于IETab实例对象进行操作
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.ie.create(url)
    page.reload()







attr(element, name, index=1, parent_element=None, timeout=10) 
-------------------------------------------------------------------------------

**方法描述** 

获取属性

**参数说明** 

**element** *\<str\>* 控件

**name** *\<str\>* 属性名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 超时时间

**返回值说明** 

返回属性 *\<str\>* 

**调用样例** - rpa.app.ie.IETab.attr-

    # 注意事项：此方法仅能基于IETab实例对象进行操作
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.ie.create(url)
    attribute = page.attr('登录按钮-ie','class')







in_view(element, index=1, parent_element=None, timeout=10) 
----------------------------------------------------------------------------

**方法描述** 

控件是否在可见区域

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 超时时间

**返回值说明** 

返回控件是否在可见区域 *\<bool\>* 

**调用样例** - rpa.app.ie.IETab.in_view-

    # 注意事项：此方法仅能基于IETab实例对象进行操作，使用前需要通过捕捉控件功能获取页面上的元素
    # 代码调用样例如下，最终会产生XX结果(即对示例代码做简要描述)
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.ie.create(url)
    flag = page.in_view('登录按钮-ie')







chrome 
========================

create(url, wait=True, timeout=100, chrome_path=None) 
-----------------------------------------------------------------------

**方法描述** 

创建chrome对象

**参数说明** 

**url** *\<str\>* 要打开的url

**wait** *\<bool\>* 是否等待加载完成

**timeout** *\<int\>* 等待超时时间, 默认100s

**chrome_path** *\<str\>* chrome.exe路径, 默认查找%ProgramFiles%, %ProgramFiles(x86)%

**返回值说明** 

返回ChromeTab对象 *\<ChromeTab\>* 

**调用样例** - rpa.app.chrome.create-

    # 注意事项：此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 代码调用样例如下：
    page = rpa.app.chrome.create('www.aliyun.com')







catch(name, mode='title', pattern='contain', timeout=10) 
--------------------------------------------------------------------------

**方法描述** 

捕获已打开的页面

**参数说明** 

**name** *\<str\>* 标题或者url

**mode** *\<str\>* 页面匹配类型

可选项：

* title : 标题

  

* url : url

  




**pattern** *\<str\>* 页面匹配模式

可选项：

* equal : 完全匹配

  

* contain : 包含匹配

  

* regular : 正则表达式匹配

  




**返回值说明** 

返回Browser对象 *\<ChromeTab\>* 

**调用样例** - rpa.app.chrome.catch-

    # 注意事项：此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件，使用前需要先确认对应网页已打开
    # 代码调用样例如下：
    page = rpa.app.chrome.catch('阿里云')







catch_specific_pages(name, mode='title', pattern='contain') 
-----------------------------------------------------------------------------

**方法描述** 

捕获满足条件的所有页面

**参数说明** 

**name** *\<str\>* 标题或者url

**mode** *\<str\>* 页面匹配类型

可选项：

* title : 标题

  

* url : url

  




**pattern** *\<str\>* 页面匹配模式

可选项：

* equal : 完全匹配

  

* contain : 包含匹配

  

* regular : 正则表达式匹配

  




**返回值说明** 

返回Browser对象的列表 *\<list\>* 

**调用样例** - rpa.app.chrome.catch_specific_pages-

    # 注意事项：此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件，使用此方法前需确认至少已打开一个符合条件的网页
    # 代码调用样例如下：
    page_list = rpa.app.chrome.catch_specific_pages('阿里云')







catch_all_pages() 
-----------------------------------

**方法描述** 

返回所有的页面

**调用样例** - rpa.app.chrome.catch_all_pages-

    # 注意事项：此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 代码调用样例如下：
    page_list = rpa.app.chrome.catch_all_pages()







catch_activated_pages() 
-----------------------------------------

**方法描述** 

返回所有激活的页面

**调用样例** - rpa.app.chrome.catch_activated_pages-

    # 注意事项：此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 当开启多个chrome浏览器程序，每个chrome程序上有多个Tab页签的情况下，可使用此方法返回每一个chrome程序中处于激活状态的Tab网页
    # 代码调用样例如下：
    page_list = rpa.app.chrome.catch_activated_pages()







close_all() 
-----------------------------

**方法描述** 

关闭所有的页面

**调用样例** - rpa.app.chrome.close_all-

    # 注意事项：此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 代码调用样例如下：
    rpa.app.chrome.close_all()







maximize() 
----------------------------

**方法描述** 

最大化浏览器窗口

**调用样例** - rpa.app.chrome.maximize-

    # 注意事项：此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 在开启多个chrome程序窗口的情况下，此方法只会将其中一个窗口最大化
    # 代码调用样例如下：
    rpa.app.chrome.maximize()







get_cookies(url=None, domain=None, name=None) 
---------------------------------------------------------------

**方法描述** 

获取一组cookie

**参数说明** 

**url** *\<str\>* 将检索到的cookie限制为与给定URL匹配的cookie

**domain** *\<str\>* 将检索到的cookie限制为域匹配或属于该域的子域的cookie

**name** *\<str\>* 按名称过滤cookie

**返回值说明** 

返回当前网站下的所有cookie *\<list\>* 

**调用样例** - rpa.app.chrome.get_cookies-

    # 注意事项：此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # url参数需要使用带协议的完整写法
    # 代码调用样例如下：
    cookies = rpa.app.chrome.get_cookies(url='https://www.aliyun.com')







remove_cookie(url, name) 
------------------------------------------

**方法描述** 

删除cookie

**参数说明** 

**url** *\<str\>* 与cookie关联的URL

**name** *\<str\>* 要删除的cookie的名称

**调用样例** - rpa.app.chrome.remove_cookie-

    # 注意事项：此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # url参数需要使用带协议的完整写法
    # 代码调用样例如下：
    rpa.app.chrome.remove_cookie('https://www.baidu.com','domain')







set_cookie(url, name, domain=None, value=None, path=None, secure=False, http_only=False, expiration_date=None) 
--------------------------------------------------------------------------------------------------------------------------------

**方法描述** 

设置cookie

**参数说明** 

**url** *\<str\>* 与cookie设置相关联的request-URI

**name** *\<str\>* cookie的名称

**domain** *\<str\>* cookie的域。如果省略，则cookie变为host-only的cookie

**value** *\<str\>* cookie的值。如果省略，默认为空

**path** *\<str\>* cookie的路径。默认为url参数的路径部分

**secure** *\<bool\>* cookie是否应标记为secure

**http_only** *\<bool\>* cookie是否应标记为http_only

**expiration_date** *\<str\>* cookie的到期日期

**调用样例** - rpa.app.chrome.set_cookie-

    # 注意事项：此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # url参数需要使用带协议的完整写法
    # 代码调用样例如下：
    rpa.app.chrome.set_cookie('https://www.baidu.com','rpa_test',value='阿里云RPA测试_www.aliyun.com')







close() 
-------------------------

**方法描述** 

关闭浏览器对象

**调用样例** - rpa.app.chrome.ChromeTab.close-

    # 注意事项：此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 此方法需要基于ChromeTab实例对象进行操作
    # 代码调用样例如下：
    page = rpa.app.chrome.create('www.aliyun.com')
    page.close()







navigate(url, wait=True, timeout=100) 
-------------------------------------------------------

**方法描述** 

跳转到指定链接

**参数说明** 

**url** *\<str\>* 要打开的url

**wait** *\<bool\>* 是否等待加载完成

**timeout** *\<int\>* 等待超时时间, 默认100s

**调用样例** - rpa.app.chrome.ChromeTab.navigate-

    # 注意事项：此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 此方法需要基于ChromeTab实例对象进行操作
    # 代码调用样例如下：
    url = 'www.aliyun.com'
    page = rpa.app.chrome.create(url)
    page.navigate('help.aliyun.com/document_detail/175379.html')







back(wait=True, timeout=100) 
----------------------------------------------

**方法描述** 

浏览器后退

**参数说明** 

**wait** *\<bool\>* 是否等待加载完成

**timeout** *\<int\>* 等待超时时间, 默认100s

**调用样例** - rpa.app.chrome.ChromeTab.back-

    # 注意事项：此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 此方法需要基于ChromeTab实例对象进行操作
    # 代码调用样例如下：
    url = 'www.aliyun.com'
    page = rpa.app.chrome.create(url)
    page.navigate('help.aliyun.com/document_detail/175379.html')
    page.back()







forward(wait=True, timeout=100) 
-------------------------------------------------

**方法描述** 

浏览器前进

**参数说明** 

**wait** *\<bool\>* 是否等待加载完成

**timeout** *\<int\>* 等待超时时间, 默认100s

**调用样例** - rpa.app.chrome.ChromeTab.forward-

    # 注意事项：此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 此方法需要基于ChromeTab实例对象进行操作
    # 代码调用样例如下：
    url = 'www.aliyun.com'
    page = rpa.app.chrome.create(url)
    page.navigate('help.aliyun.com/document_detail/175379.html')
    page.back()
    page.forward()







activate() 
----------------------------

**方法描述** 

激活页面

**调用样例** - rpa.app.chrome.ChromeTab.activate-

    # 注意事项：此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 此方法需要基于ChromeTab实例对象进行操作
    # 代码调用样例如下：
    url = 'www.aliyun.com'
    page = rpa.app.chrome.create(url)
    page.activate()







url() 
-----------------------

**方法描述** 

获取url

**返回值说明** 

返回url *\<str\>* 

**调用样例** - rpa.app.chrome.ChromeTab.url-

    # 注意事项：此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 此方法需要基于ChromeTab实例对象进行操作
    # 代码调用样例如下：
    page = rpa.app.chrome.create('www.aliyun.com')
    url = page.url()







title() 
-------------------------

**方法描述** 

获取title

**返回值说明** 

返回标题 *\<str\>* 

**调用样例** - rpa.app.chrome.ChromeTab.title-

    # 注意事项：此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 此方法需要基于ChromeTab实例对象进行操作
    # 代码调用样例如下：
    page = rpa.app.chrome.create('www.aliyun.com')
    title= page.title()







reload(bypass_cache=False, wait=True, timeout=100) 
--------------------------------------------------------------------

**方法描述** 

刷新页面

**参数说明** 

**bypass_cache** *\<bool\>* 是否忽略缓存

**wait** *\<bool\>* 是否等待加载完成

**timeout** *\<int\>* 等待超时时间, 默认100s

**调用样例** - rpa.app.chrome.ChromeTab.reload-

    # 注意事项：此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 此方法需要基于ChromeTab实例对象进行操作
    # 代码调用样例如下：
    page = rpa.app.chrome.create('www.aliyun.com')
    page.reload()







get_cookie() 
------------------------------

**方法描述** 

获取当前网站下的所有Cookie

**返回值说明** 

返回当前网站下的所有Cookie *\<list\>* 

**调用样例** - rpa.app.chrome.ChromeTab.get_cookie-

    # 注意事项：此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 此方法需要基于ChromeTab实例对象进行操作
    # 代码调用样例如下：
    page = rpa.app.chrome.create('www.aliyun.com')
    cookie = page.get_cookie()







wait_load_completed(timeout=100) 
--------------------------------------------------

**方法描述** 

等待页面加载完成

**参数说明** 

**timeout** *\<int\>* 等待超时时间, 默认100s

**调用样例** - rpa.app.chrome.ChromeTab.wait_load_completed-

    # 注意事项：此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 此方法需要基于ChromeTab实例对象进行操作
    # 代码调用样例如下：
    page = rpa.app.chrome.create('www.aliyun.com')
    page.wait_load_completed()







copy() 
------------------------

**方法描述** 

在当前页面上执行拷贝操作

**返回值说明** 

返回操作是否成功 *\<bool\>* 

**调用样例** - rpa.app.chrome.ChromeTab.copy-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 此方法仅执行复制指令，需要通过其他方法选中待复制的内容后，再执行此方法。
    # 3. 此方法会将内容写入到系统剪贴板。
    # 代码调用样例如下，本例中，通过双击的形式点击单元格内容，选中了对应文本，再执行复制操作：
    page = rpa.app.chrome.create('https://help.aliyun.com/document_detail/175379.html')
    page.double_click('queryClientViews-chrome')
    page.copy()







paste() 
-------------------------

**方法描述** 

在当前页面上执行粘贴操作

**返回值说明** 

返回操作是否成功 *\<bool\>* 

**调用样例** - rpa.app.chrome.ChromeTab.paste-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 此方法仅执行粘贴指令，需要通过其他方法选中待粘贴区域后，再执行此方法。
    # 3. 此方法会将剪贴板上的最新内容粘贴到对应区域。
    # 代码调用样例如下，本例中，复制了单元格内容之后，点击了搜索框，再执行粘贴动作：
    page = rpa.app.chrome.create('https://help.aliyun.com/document_detail/175379.html')
    page.double_click('queryClientViews-chrome')
    page.copy()
    page.click('文档搜索框-chrome')
    page.paste()







cut() 
-----------------------

**方法描述** 

在当前页面上执行剪切操作

**返回值说明** 

返回操作是否成功 *\<bool\>* 

**调用样例** - rpa.app.chrome.ChromeTab.cut-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 此方法仅执行剪切指令，需要通过其他方法选中可剪切内容后，再执行此方法（如果内容本身不可剪贴，此动作将无效）
    # 3. 此方法会将内容写入到系统剪贴板。
    # 代码调用样例如下，本例中，需先人工打开百度首页，并在输入框中输入任意内容，
    # 程序会双击输入框获取其中的文本，再执行剪切动作：
    page = rpa.app.chrome.catch('www.baidu.com',mode='url')
    page.double_click('百度输入框-chrome')
    page.cut()







execute_js(code, element=None, index=1, timeout=10) 
---------------------------------------------------------------------

**方法描述** 

执行js代码

**参数说明** 

**code** *\<str\>* js代码

**element** *\<str\>* 控件, 在此控件所在域内执行JS(用于跨域)

**index** *\<int\>* 如果有多个，给出控件下标

**timeout** *\<int\>* 超时时间

**返回值说明** 

返回执行结果(JSON字符串形式) *\<str\>* 

**调用样例** - rpa.app.chrome.ChromeTab.execute_js-

    # 注意事项：此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 此方法需要基于ChromeTab实例对象进行操作
    # 代码调用样例如下：
    js_code = """
    function test(){ 
        var div1 = document.getElementById("su");return(div1) 
        } ; 
    result = test() ; 
    console.log(result) ; 
    alert(result)
    """
    
    url = 'www.baidu.com'
    page = rpa.app.chrome.create(url)
    
    page.execute_js(js_code)







table(value, type='index', return_type='text', parent_element=None) 
-------------------------------------------------------------------------------------

**方法描述** 

获取表格

**参数说明** 

**type** *\<str\>* 匹配类型

可选项：

* index : 下标匹配

  

* text : 文本匹配

  

* html : html匹配

  




**return_type** *\<str\>* 返回类型

可选项：

* text : 文本类型

  

* html : html类型

  




**返回值说明** 

返回匹配成功table对应的二维数组或html *\<list\>* 

**调用样例** - rpa.app.chrome.ChromeTab.table-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 此方法根据索引（从1开始）或者正则表达式获取页面上的标准表格（html标签为table）
    # 代码调用样例如下，运行后会获取网页上第1个表格（按html从上至下的顺序，第1个table标签的内容）：
    page = rpa.app.chrome.create('https://help.aliyun.com/document_detail/175379.html')
    table_data = page.table(1)







scroll(height=0, element=None, index=1, parent_element=None, timeout=10, direction='top') 
-----------------------------------------------------------------------------------------------------------

**方法描述** 

滚动页面

**参数说明** 

**height** *\<int\>* 设置则滚动指定高度，否则滚动到页面最底部

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 超时时间

**direction** *\<str\>* 选择滚动条方向

可选项：

* left : 向左滚动

  

* top : 向下滚动

  




**调用样例** - rpa.app.chrome.ChromeTab.scroll-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 不传参数或者参数设为0时，此方法会将滑块滚动到底端。
    # 代码调用样例如下：
    page = rpa.app.chrome.create('https://help.aliyun.com/document_detail/175379.html')
    page.scroll()







download_by_url(url, path, wait=True, complete_timeout=120) 
-----------------------------------------------------------------------------

**方法描述** 

根据url下载文件(前提设置，进入chrome://settings/, 取消"下载前询问每个文件的保存位置")

**参数说明** 

**url** *\<str\>* 下载文件的链接

**path** *\<str\>* 保存的文件路径

**complete_timeout** *\<int\>* 超时时间

**wait** *\<bool\>* 是否等待完成

**调用样例** - rpa.app.chrome.ChromeTab.download_by_url-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 代码调用样例如下，运行后会下载对应文件到指定路径：
    url = 'www.cninfo.com.cn'
    page = rpa.app.chrome.create(url)
    download_url = 'www.cninfo.com.cn/new/announcement/download?bulletinId=1209275224&announceTime=2021-02-10'
    download_path = r'D:\阿里巴巴-SW.pdf'
    page.download_by_url(download_url,download_path)







get_element_by_name(element, index=1, parent_element=None, timeout=10) 
----------------------------------------------------------------------------------------

**方法描述** 

获取控件对象

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<str\>* 父控件对象

**timeout** *\<int\>* 超时时间

**返回值说明** 

返回控件对象 *\<Element\>* 

**调用样例** - rpa.app.chrome.ChromeTab.get_element_by_name-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要先通过捕捉控件功能获取页面上的下载按钮并验证可用
    # 代码调用样例如下，运行后会下载对应文件到指定路径：
    url = 'http://www.cninfo.com.cn/new/disclosure/detail?plate=hke&orgId=9900042435&stockCode=09988&announcementId=1209275224'
    page = rpa.app.chrome.create(url)
    download_path = r'D:\阿里巴巴-SW-公开资料.pdf'
    page.download_by_element(download_path , '公告下载-chrome')







get_element_by_css(css, index=1, parent_element=None, timeout=10) 
-----------------------------------------------------------------------------------

**方法描述** 

根据CSS表达式获取控件

**参数说明** 

**css** *\<str\>* CSS表达式

**index** *\<int\>* 如果有多个，给出控件下标

**parent_elemet** *\<str\>* 父控件对象

**timeout** *\<int\>* 超时时间

**返回值说明** 

返回控件对象 *\<Element\>* 

**调用样例** - rpa.app.chrome.ChromeTab.get_element_by_css-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 此方法使用css选择器定位要操作的元素，请使用标准的css-selector表达式
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.chrome.create(url)
    css_selector = "span.menu-title-text"
    element = page.get_element_by_css(css_selector)
    text = element.text()







count(element, parent_element=None) 
-----------------------------------------------------

**方法描述** 

获取控件个数

**参数说明** 

**element** *\<str\>* 控件

**parent_elemet** *\<str\>* 父控件对象

**调用样例** - rpa.app.chrome.ChromeTab.count-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 通过捕捉相似控件功能获取相似控件元素后，常使用此方法统计控件数量
    # 代码调用样例如下：
    url = 'www.aliyun.com'
    page = rpa.app.chrome.create(url)
    element_count = page.count('登录按钮-chrome')







wait_loaded(element, index=1, parent_element=None, timeout=10, ignore_error=True) 
---------------------------------------------------------------------------------------------------

**方法描述** 

等待控件加载

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<str\>* 父控件对象

**timeout** *\<int\>* 超时时间

**ignore_error** *\<bool\>* 忽略错误

**调用样例** - rpa.app.chrome.ChromeTab.wait_loaded-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    page = rpa.app.chrome.create('www.taobao.com')
    flag = page.wait_loaded('淘宝logo')







wait_disappear(element, index=1, parent_element=None, timeout=10) 
-----------------------------------------------------------------------------------

**方法描述** 

等待控件消失

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<str\>* 父控件对象

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.app.chrome.ChromeTab.wait_disappear-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    page = rpa.app.chrome.create('www.taobao.com')
    flag = page.wait_disappear('淘宝logo')







handle_javascript_dialog(value='ok', text=None) 
-----------------------------------------------------------------

**方法描述** 

处理JavaScript弹出框

**参数说明** 

**value** *\<str\>* 弹出框处理

可选项：

* ok : 点击确定

  

* cancel : 点击取消

  




**text** *\<str\>* 向弹框中输入的文本

**调用样例** - rpa.app.chrome.ChromeTab.handle_javascript_dialog-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 代码调用样例如下：
    url = 'www.baidu.com'
    page = rpa.app.chrome.create(url)
    page.execute_js('alert("阿里云RPA_TEST")')
    page.handle_javascript_dialog()







click(element, index=1, parent_element=None, simulate=True, button='left', offset_x=0, offset_y=0, timeout=10) 
--------------------------------------------------------------------------------------------------------------------------------

**方法描述** 

点击

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<str\>* 父控件对象

**simulate** *\<bool\>* 是否模拟点击

**button** *\<str\>* 鼠标键位

可选项：

* left : 左键

  

* right : 右键

  




**offset_x** *\<int\>* 横向偏移

**offset_y** *\<int\>* 纵向偏移

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.app.chrome.ChromeTab.click-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 3. simulate=True，即模拟点击情况下，需要对应的页面元素在可见区域，模拟鼠标点击
    # 4. simulate=False，即在非模拟点击情况下，将直接向元素发送对应点击指令
    # 代码调用样例如下：
    url = 'www.aliyun.com'
    page = rpa.app.chrome.create(url)
    page.click('登录按钮-chrome')







input_text(element, value, index=1, parent_element=None, simulate=True, replace=True, sent_raw=False, wait_mili_seconds=20, timeout=10) 
---------------------------------------------------------------------------------------------------------------------------------------------------------

**方法描述** 

输入文本

**参数说明** 

**element** *\<str\>* 控件

**value** *\<str\>* 输入的内容

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<str\>* 父控件对象

**simulate** *\<bool\>* 是否模拟输入

**replace** *\<bool\>* 是否清空之前的内容

**sent_raw** *\<bool\>* 是否发送原始按键，仅非模拟模式有效

**wait_mili_seconds** *\<int\>* 字符间输入间隔（毫秒），仅在模拟输入下有效，默认值为20，最大值100，该值设置过大可能会引起超时

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.app.chrome.ChromeTab.input_text-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    url = 'www.taobao.com'
    page = rpa.app.chrome.create(url)
    page.input_text('淘宝搜索框-chrome','RPA')







input_hotkeys(element, value, index=1, parent_element=None, timeout=10) 
-----------------------------------------------------------------------------------------

**方法描述** 

输入快捷键

**参数说明** 

**element** *\<str\>* 控件

**value** *\<str\>* 输入的内容

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<str\>* 父控件对象

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.app.chrome.ChromeTab.input_hotkeys-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 3. 虚拟键写法请参考：虚拟键列表参考 https://www.yuque.com/aliyun_rpa/quzm63/vk
    # 代码调用样例如下：
    url = 'www.taobao.com'
    page = rpa.app.chrome.create(url)
    page.input_text('淘宝搜索框-ie','RPA')
    page.input_hotkeys('淘宝搜索框-ie','VK_RETURN')







download_by_element(path, element, index=1, parent_element=None, wait=True, complete_timeout=120) 
-------------------------------------------------------------------------------------------------------------------

**方法描述** 

根据控件下载文件，并等待下载结束(前提设置，进入chrome://settings/, 取消"下载前询问每个文件的保存位置")

**参数说明** 

**path** *\<str\>* 保存的文件路径

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**complete_timeout** *\<int\>* 超时时间

**wait** *\<bool\>* 是否等待完成

**调用样例** - rpa.app.chrome.ChromeTab.download_by_element-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要先通过捕捉控件功能获取页面上的下载按钮并验证可用
    # 代码调用样例如下：
    url = 'http://www.cninfo.com.cn/new/disclosure/detail?plate=hke&orgId=9900042435&stockCode=09988&announcementId=1209275224'
    page = rpa.app.chrome.create(url)
    download_path = r'D:\阿里巴巴-SW-公开资料.pdf'
    page.download_by_element(download_path,'公告下载-chrome')







upload(element, file, index=1, parent_element=None, timeout=10) 
---------------------------------------------------------------------------------

**方法描述** 

上传文件

**参数说明** 

**element** *\<str\>* 控件

**file** *\<str\>* 上传的文件路径

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<str\>* 父控件对象

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.app.chrome.ChromeTab.upload-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要先通过捕捉控件功能获取页面上的上传按钮并验证可用
    # 代码调用样例如下：
    url = 'https://duguang.aliyun.com/experience?type=standard&subtype=idcard#intro'
    page = rpa.app.chrome.create(url)
    upload_path = r'D:\2_测试文件归档\OCR身份证识别.jpg'
    page.upload('上传图片-chrome',upload_path)







text(element=None, index=1, parent_element=None, timeout=10) 
------------------------------------------------------------------------------

**方法描述** 

获取文本

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<str\>* 父控件对象

**timeout** *\<int\>* 超时时间

**返回值说明** 

返回文本，不传控件则返回浏览器上所有的文本 *\<str\>* 

**调用样例** - rpa.app.chrome.ChromeTab.text-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.chrome.create(url)
    text = page.text(element='网页底部-售前咨询-chrome')







html(element=None, index=1, parent_element=None, timeout=10) 
------------------------------------------------------------------------------

**方法描述** 

获取html

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<str\>* 父控件对象

**timeout** *\<int\>* 超时时间

**返回值说明** 

返回html，不传控件则返回浏览器上所有的html *\<str\>* 

**调用样例** - rpa.app.chrome.ChromeTab.html-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.chrome.create(url)
    html = page.html('网页底部-售前咨询-chrome')







value(element, index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------

**方法描述** 

获取值

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<str\>* 父控件对象

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.app.chrome.ChromeTab.value-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.chrome.create(url)
    value = page.value('网页底部-售前咨询-chrome')







option(element, text, index=1, parent_element=None, type='match', timeout=10) 
-----------------------------------------------------------------------------------------------

**方法描述** 

下拉框选择

**参数说明** 

**element** *\<str\>* 控件

**text** *\<str\>* 选择内容

**index** *\<int\>* 如果有多个，给出控件下标

**type** *\<str\>* 匹配类型

可选项：

* match : 模糊匹配

  

* full : 完全匹配

  

* regex : 正则匹配

  




**parent_element** *\<str\>* 父控件对象

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.app.chrome.ChromeTab.option-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要先通过捕捉控件功能获取页面标准下拉框元素(html标签为select)
    # 3. 需确认下拉框中存在对应的文本选项
    # 代码调用样例如下：
    url = 'https://kyfw.12306.cn/otn/leftTicket/init'
    page = rpa.app.chrome.create(url)
    
    page.option('下拉框-ie','00:00--06:00')









get_checked_state(element, index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------------------

**方法描述** 

获取勾选状态

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<str\>* 父控件对象

**timeout** *\<int\>* 超时时间

**返回值说明** 

返回勾选状态 *\<bool\>* 

**调用样例** - rpa.app.chrome.ChromeTab.get_checked_state-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    url = 'https://kyfw.12306.cn/otn/leftTicket/init'
    page = rpa.app.chrome.create(url)
    check_state = page.get_checked_state('复选框-动车-chrome')









set_checked_state(element, value=True, index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------------------------------

**方法描述** 

设置勾选状态

**参数说明** 

**element** *\<str\>* 控件

**value** *\<bool\>* 传入True则勾选，传入False取消勾选

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<str\>* 父控件对象

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.app.chrome.ChromeTab.set_checked_state-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    url = 'https://kyfw.12306.cn/otn/leftTicket/init'
    page = rpa.app.chrome.create(url)
    check_state = page.set_checked_state('复选框-动车-chrome')







attr(element, attrname, index=1, parent_element=None, timeout=10) 
-----------------------------------------------------------------------------------

**方法描述** 

获取属性

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<str\>* 父控件对象

**timeout** *\<int\>* 超时时间

**返回值说明** 

返回属性值 *\<str\>* 

**调用样例** - rpa.app.chrome.ChromeTab.attr-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.chrome.create(url)
    attribute = page.attr('登录按钮-chrome','class')







process_alert(option='ok', element=None, simulate=True, index=1, parent_element=None, timeout=10) 
-------------------------------------------------------------------------------------------------------------------

**方法描述** 

弹出框点击

**参数说明** 

**value** *\<str\>* 弹出框处理

可选项：

* ok : 点击确定

  

* cancel : 点击取消

  




**element** *\<str\>* 控件(不传控件则为浏览器内的弹出框点击)

**simulate** *\<bool\>* 是否模拟

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.app.chrome.ChromeTab.process_alert-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 此方法仅能处理confirm或alert弹窗
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.chrome.create(url)
    page.execute_js('alert("提示框")')
    page.process_alert()







process_prompt(text, option='ok', element=None, simulate=True, index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------------------------------------------------------

**方法描述** 

输入框输入并点击

**参数说明** 

**text** *\<str\>* 输入内容

**option** *\<str\>* 输入框点击

可选项：

* ok : 点击确定

  

* cancel : 点击取消

  




**element** *\<str\>* 控件(不传控件则为浏览器内的弹出框点击)

**simulate** *\<bool\>* 是否模拟

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.app.chrome.ChromeTab.process_prompt-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 此方法仅能处理prompt弹窗
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.chrome.create(url)
    page.execute_js('prompt("请输入内容：","")')
    page.process_prompt('RPA_TEST')







pos(element, index=1, parent_element=None, timeout=10) 
------------------------------------------------------------------------

**方法描述** 

获取控件坐标

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<str\>* 父控件对象

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.app.chrome.ChromeTab.pos-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 此方法返回的坐标是以屏幕左上角为原点，页面元素的坐标------即移动网页窗口，此坐标会变化
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.chrome.create(url)
    pos = page.pos('登录按钮-chrome')







screenshot(element, file, index=1, parent_element=None, timeout=10) 
-------------------------------------------------------------------------------------

**方法描述** 

截图

**参数说明** 

**element** *\<str\>* 控件

**file** *\<str\>* 保存的截图路径

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<str\>* 父控件对象

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.app.chrome.ChromeTab.screenshot-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.chrome.create(url)
    save_path = r'D:\阿里云底部文本截图.jpg'
    page.screenshot('网页底部-售前咨询-chrome',save_path)







mouse_move(element, index=1, parent_element=None, timeout=10) 
-------------------------------------------------------------------------------

**方法描述** 

鼠标移入

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<str\>* 父控件对象

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.app.chrome.ChromeTab.mouse_move-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.chrome.create(url)
    page.mouse_move('网页底部-售前咨询-chrome')







isvisible(element, index=1, parent_element=None, timeout=10) 
------------------------------------------------------------------------------

**方法描述** 

获取控件是否可见

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<str\>* 父控件对象

**timeout** *\<int\>* 超时时间

**返回值说明** 

返回是否可见 *\<bool\>* 

**调用样例** - rpa.app.chrome.ChromeTab.isvisible-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 3. 此方法判断的是页面元素的可见属性，如果页面本身不存在对应元素，则会抛出等待控件超时异常
    # 代码调用样例如下，本例中打开网页后，使用js将指定页面元素设为不可见，再使用此方法：
    url = 'www.baidu.com'
    page = rpa.app.chrome.create(url)
    js = """
    function set_display(){
        var div1 = document.getElementById("su");
        div1.style.display = "none";
    };
    set_display()
    """
    page.execute_js(js)
    
    flag = page.isvisible('百度一下-chrome')









drag(element, x=0, y=0, index=1, parent_element=None, timeout=10) 
-----------------------------------------------------------------------------------

**方法描述** 

将元素拖拽指定的偏移量

**参数说明** 

**element** *\<str\>* 控件

**x** *\<int\>* x轴偏移量

**y** *\<int\>* y轴偏移量

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<str\>* 父控件对象

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.app.chrome.ChromeTab.drag-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.chrome.create(url)
    page.drag('登录按钮-chrome',x=-500,y=100)







clear_input(element, index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------------

**方法描述** 

清空输入框

**参数说明** 

**element** *\<str\>* 控件

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<str\>* 父控件对象

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.app.chrome.ChromeTab.clear_input-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    url = 'www.baidu.com'
    page = rpa.app.chrome.create(url)
    page.clear_input('百度一下-chrome')







scroll_into_view() 
------------------------------------

**方法描述** 

将元素调整到可视区域

**调用样例** - rpa.app.chrome.ChromeTab.ChromeElement.scroll_into_view-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.chrome.create(url)
    element = page.get_element_by_name('网页底部-售前咨询-chrome')
    element.scroll_into_view()







click(simulate=True, button='left', offset_x=0, offset_y=0) 
-----------------------------------------------------------------------------

**方法描述** 

点击

**参数说明** 

**simulate** *\<bool\>* 是否模拟点击

**button** *\<str\>* 鼠标键位

可选项：

* left : 左键

  

* right : 右键

  




**offset_x** *\<int\>* 横向偏移

**offset_y** *\<int\>* 纵向偏移

**调用样例** - rpa.app.chrome.ChromeTab.ChromeElement.click-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.chrome.create(url)
    element = page.get_element_by_name('登录按钮-chrome')
    
    element.click()







double_click(simulate=True, offset_x=0, offset_y=0) 
---------------------------------------------------------------------

**方法描述** 

双击

**参数说明** 

**simulate** *\<bool\>* 是否模拟点击

**offset_x** *\<int\>* 横向偏移

**offset_y** *\<int\>* 纵向偏移

**调用样例** - rpa.app.chrome.ChromeTab.ChromeElement.double_click-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.chrome.create(url)
    element = page.get_element_by_name('queryClientViews-chrome')
    
    element.double_click()







input_text(value, simulate=True, replace=True, sent_raw=False, wait_mili_seconds=20) 
------------------------------------------------------------------------------------------------------

**方法描述** 

输入文本

**参数说明** 

**value** *\<str\>* 输入的内容

**simulate** *\<bool\>* 是否模拟输入

**replace** *\<bool\>* 是否清空之前的内容

**sent_raw** *\<bool\>* 是否发送原始按键，仅非模拟模式有效

**wait_mili_seconds** *\<int\>* 字符间输入间隔（毫秒），仅在模拟输入下有效，默认值为20，最大值100，该值设置过大可能会引起超时

**调用样例** - rpa.app.chrome.ChromeTab.ChromeElement.input_text-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    url = 'www.baidu.com'
    page = rpa.app.chrome.create(url)
    element = page.get_element_by_name('百度输入框-chrome')
    
    element.input_text('阿里云RPA')







input_hotkeys(value) 
--------------------------------------

**方法描述** 

输入快捷键

**参数说明** 

**value** *\<str\>* 输入的内容

**调用样例** - rpa.app.chrome.ChromeTab.ChromeElement.input_hotkeys-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 3. 虚拟键码表请参考：https://www.yuque.com/aliyun_rpa/quzm63/vk
    # 代码调用样例如下：
    url = 'www.taobao.com'
    page = rpa.app.chrome.create(url)
    element = page.get_element_by_name('淘宝输入框-chrome')
    element.input_text('阿里云')
    
    element = input_hotkeys('VK_RETURN')







download(path, prepare_timeout=10, complete_timeout=120) 
--------------------------------------------------------------------------

**方法描述** 

点击控件开始下载，并等待下载结束

**参数说明** 

**path** *\<str\>* 下载结果存放的完整文件路径

**prepare_timeout** *\<int\>* 等待进入下载的超时时间

**complete_timeout** *\<int\>* 等待下载完成的超时时间

**返回值说明** 

返回是否下载成功 *\<bool\>* 

**调用样例** - rpa.app.chrome.ChromeTab.ChromeElement.download-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    url = 'http://www.cninfo.com.cn/new/disclosure/detail?plate=hke&orgId=9900042435&stockCode=09988&announcementId=1209275224'
    page = rpa.app.chrome.create(url)
    element = page.get_element_by_name('公告下载-chrome')
    download_path = r'D:\阿里巴巴-SW-公开资料.pdf'
    
    element.download(download_path)









upload(file) 
------------------------------

**方法描述** 

点击控件开始上传，并等待上传结束

**参数说明** 

**file** *\<str\>* 上传文件完整路径

**调用样例** - rpa.app.chrome.ChromeTab.ChromeElement.upload-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    url = 'https://duguang.aliyun.com/experience?type=standard&subtype=idcard#intro'
    page = rpa.app.chrome.create(url)
    upload_path = r'D:\2_测试文件归档\OCR身份证识别.jpg'
    element = page.get_element_by_name('上传图片-chrome')
    
    element .upload(upload_path)







execute_js(code) 
----------------------------------

**方法描述** 

执行js代码

**参数说明** 

**code** *\<str\>* js代码

**返回值说明** 

返回执行结果(JSON字符串形式) *\<str\>* 

**调用样例** - rpa.app.chrome.ChromeTab.ChromeElement.execute_js-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    url = 'www.baidu.com'
    page = rpa.app.chrome.create(url)
    js = """
    var div1 = document.getElementById("su");
    div1.style.display = "none";
    """
    element = page.get_element_by_name('百度一下-chrome')
    
    element.execute_js(js)







text() 
------------------------

**方法描述** 

获取元素内容文本

**返回值说明** 

返回元素内容文本 *\<str\>* 

**调用样例** - rpa.app.chrome.ChromeTab.ChromeElement.text-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    url = 'www.baidu.com'
    page = rpa.app.chrome.create(url)
    element = page.get_element_by_name('百度一下-chrome')
    
    text = element.text()







html() 
------------------------

**方法描述** 

获取元素HTML源代码

**返回值说明** 

返回元素内容文本 *\<str\>* 

**调用样例** - rpa.app.chrome.ChromeTab.ChromeElement.html-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    url = 'www.baidu.com'
    page = rpa.app.chrome.create(url)
    element = page.get_element_by_name('百度一下-chrome')
    
    html= element.html()







value() 
-------------------------

**方法描述** 

获取元素值

**返回值说明** 

返回元素值 *\<str\>* 

**调用样例** - rpa.app.chrome.ChromeTab.ChromeElement.value-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 3. 此方法获取的是对应元素的html标签中value属性的值
    # 代码调用样例如下：
    url = 'www.baidu.com'
    page = rpa.app.chrome.create(url)
    element = page.get_element_by_name('百度一下-chrome')
    
    value= element.value()







option(text, type='match') 
--------------------------------------------

**方法描述** 

通过文本下拉框选择

**参数说明** 

**text** *\<str\>* 选择内容

**type** *\<str\>* 匹配类型

可选项：

* match : 模糊匹配

  

* full : 完全匹配

  

* regex : 正则匹配

  




**调用样例** - rpa.app.chrome.ChromeTab.ChromeElement.option-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 3. 需确认下拉框中存在对应的文本选项
    # 代码调用样例如下：
    url = 'https://kyfw.12306.cn/otn/leftTicket/init'
    page = rpa.app.chrome.create(url)
    element = page.get_element_by_name('下拉框-时刻表-chrome')
    
    element.option('00:00--06:00')







option_by_index(item_index) 
---------------------------------------------

**方法描述** 

通过索引设置下拉框选项

**参数说明** 

**item_index** *\<int\>* 选项索引，从1开始

**调用样例** - rpa.app.chrome.ChromeTab.ChromeElement.option_by_index-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 3. 需确认下拉框中选项个数，索引从1计算，不能超过选项最大个数
    # 代码调用样例如下：
    url = 'https://kyfw.12306.cn/otn/leftTicket/init'
    page = rpa.app.chrome.create(url)
    element = page.get_element_by_name('下拉框-时刻表-chrome')
    
    element.option_by_index(2)







get_options(mode='selected') 
----------------------------------------------

**方法描述** 

返回下拉框选中的值/所有的选项

**参数说明** 

**mode** *\<str\>* 返回类型

可选项：

* selected : 选中项

  

* all : 所有项

  




**返回值说明** 

返回选项集合 *\<list\>* 

**调用样例** - rpa.app.chrome.ChromeTab.ChromeElement.get_options-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    url = 'https://kyfw.12306.cn/otn/leftTicket/init'
    page = rpa.app.chrome.create(url)
    element = page.get_element_by_name('下拉框-时刻表-chrome')
    
    options = element.get_options()







get_checked_state() 
-------------------------------------

**方法描述** 

获取勾选状态

**返回值说明** 

返回勾选状态 *\<bool\>* 

**调用样例** - rpa.app.chrome.ChromeTab.ChromeElement.get_checked_state-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    url = 'https://kyfw.12306.cn/otn/leftTicket/init'
    page = rpa.app.chrome.create(url)
    element = page.get_element_by_name('复选框-动车-chrome')
    
    check_state = element.get_checked_state()







set_checked_state(value=True) 
-----------------------------------------------

**方法描述** 

设置勾选状态

**参数说明** 

**value** *\<bool\>* 传入True则勾选，传入False取消勾选

**调用样例** - rpa.app.chrome.ChromeTab.ChromeElement.set_checked_state-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    url = 'https://kyfw.12306.cn/otn/leftTicket/init'
    page = rpa.app.chrome.create(url)
    element = page.get_element_by_name('复选框-动车-chrome')
    
    element.set_checked_state(False)







attr(name) 
----------------------------

**方法描述** 

获取属性

**参数说明** 

**name** *\<str\>* 属性名

**返回值说明** 

返回属性 *\<str\>* 

**调用样例** - rpa.app.chrome.ChromeTab.ChromeElement.attr-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.chrome.create(url)
    element = page.get_element_by_name('登录按钮-chrome')
    
    attribute = element.attr('class')







pos() 
-----------------------

**方法描述** 

获取控件坐标

**调用样例** - rpa.app.chrome.ChromeTab.ChromeElement.pos-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.chrome.create(url)
    element = page.get_element_by_name('登录按钮-chrome')
    
    pos_dict = element.pos()







screenshot(file) 
----------------------------------

**方法描述** 

控件截图

**参数说明** 

**file** *\<str\>* 保存的截图路径

**调用样例** - rpa.app.chrome.ChromeTab.ChromeElement.screenshot-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.chrome.create(url)
    element = page.get_element_by_name('登录按钮-chrome')
    save_path = r'D:\阿里云登录按钮.jpg'
    
    element .screenshot(save_path)







mouse_move() 
------------------------------

**方法描述** 

鼠标移入

**调用样例** - rpa.app.chrome.ChromeTab.ChromeElement.mouse_move-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.chrome.create(url)
    element = page.get_element_by_name('登录按钮-chrome')
    
    element .mouse_move()







isvisible() 
-----------------------------

**方法描述** 

获取控件是否可见

**返回值说明** 

返回控件是否可见 *\<bool\>* 

**调用样例** - rpa.app.chrome.ChromeTab.ChromeElement.isvisible-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下，本例中先使用js代码将元素设为不可见，然后再使用此方法：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.chrome.create(url)
    element = page.get_element_by_name('登录按钮-chrome')
    js = """
    var div1 = document.getElementById("su");
    div1.style.display = "none";
    """
    element.excute_js(js)
    
    flag = element.isvisible()







drag(x=0, y=0) 
--------------------------------

**方法描述** 

将元素拖拽到指定的位置

**参数说明** 

**x** *\<int\>* x轴偏移量

**y** *\<int\>* y轴偏移量

**调用样例** - rpa.app.chrome.ChromeTab.ChromeElement.drag-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    url = 'https://help.aliyun.com/document_detail/175379.html'
    page = rpa.app.chrome.create(url)
    element = page.get_element_by_name('登录按钮-chrome')
    
    element.drag(x=-500,y=100)







clear() 
-------------------------

**方法描述** 

清空输入框

**调用样例** - rpa.app.chrome.ChromeTab.ChromeElement.clear-

    # 注意事项：
    # 1. 此方法需要确认已安装并启用Aliyun RPA对应的chrome扩展插件
    # 2. 使用前需要确认已通过捕捉控件功能录制了页面元素
    # 代码调用样例如下：
    url = 'www.baidu.com'
    page = rpa.app.chrome.create(url)
    element = page.get_element_by_name('百度输入框-chrome')
    
    element.clear()







sap 
=====================

session(con_index=0, ses_index=0, win_title=None) 
-------------------------------------------------------------------

**方法描述** 

创建SAP Session

**参数说明** 

**con_index** *\<int\>* SAP GuiConnection 索引

**ses_index** *\<int\>* SAP GuiSession 索引

**win_title** *\<str\>* SAP 窗体标题

**返回值说明** 

返回Session对象 *\<\>* 

**调用样例** - rpa.app.sap.session-

    # 注意事项：使用此方法前请确认安装并打开了sapGUI窗口，使用参数win_tilte指定对应窗口
    # 代码调用样例如下：
    sap_session = rpa.app.sap.session(win_title="SAPXX")







input_text(element, value) 
--------------------------------------------

**方法描述** 

向控件输入

**参数说明** 

**element** *\<str\>* 控件名

**value** *\<str\>* 输入的内容

**调用样例** - rpa.app.sap._SapSession.input_text-

    # 注意事项：此方法需要基于sap的session对象操作，请先通过捕捉控件功能捕捉要操作的页面元素
    # 代码调用样例如下：
    sap_session = rpa.app.sap.session(win_title="SAPXX")
    
    sap_session.input_text("事务代码输入框", "FB50")







click(element) 
--------------------------------

**方法描述** 

单击控件

**参数说明** 

**element** *\<str\>* 控件名

**调用样例** - rpa.app.sap._SapSession.click-

    # 注意事项：此方法需要基于sap的session对象操作，请先通过捕捉控件功能捕捉要操作的页面元素
    # 代码调用样例如下：
    sap_session = rpa.app.sap.session(win_title="SAPXX")
    
    sap_session.click("执行按钮")







text(element) 
-------------------------------

**方法描述** 

获取控件内容

**参数说明** 

**element** *\<str\>* 控件名

**调用样例** - rpa.app.sap._SapSession.text-

    # 注意事项：此方法需要基于sap的session对象操作，请先通过捕捉控件功能捕捉要操作的页面元素
    # 代码调用样例如下：
    sap_session = rpa.app.sap.session(win_title="SAPXX")
    
    sap_session.text("事务处理选项")







check(element, value=None) 
--------------------------------------------

**方法描述** 

勾选

**参数说明** 

**element** *\<str\>* 控件名

**value** *\<bool\>* 是否勾选

**调用样例** - rpa.app.sap._SapSession.check-

    # 注意事项：此方法需要基于sap的session对象操作，请先通过捕捉控件功能捕捉要操作的页面元素
    # 代码调用样例如下：
    sap_session = rpa.app.sap.session(win_title="SAPXX")
    
    check_flag = sap_session.check("勾选按钮")
    sap_session.check("勾选按钮", value=False)







option(element, value, key=None) 
--------------------------------------------------

**方法描述** 

选择

**参数说明** 

**element** *\<str\>* 控件名

**value** *\<str\>* 要选择项的文本

**key** *\<str\>* 要选择项的key值

**调用样例** - rpa.app.sap._SapSession.option-

    # 注意事项：此方法需要基于sap的session对象操作，请先通过捕捉控件功能捕捉要操作的页面元素
    # 代码调用样例如下：
    sap_session = rpa.app.sap.session(win_title="SAPXX")
    
    sap_session.option("下拉框控件")







open_dialog(element) 
--------------------------------------

**方法描述** 

打开控件的对话框

**参数说明** 

**element** *\<str\>* 控件名

**调用样例** - rpa.app.sap._SapSession.open_dialog-

    # 注意事项：此方法需要基于sap的session对象操作，请先通过捕捉控件功能捕捉要操作的页面元素
    # 代码调用样例如下：
    sap_session = rpa.app.sap.session(win_title="SAPXX")
    
    sap_session.open_dialog("对话框控件")







send_vkey(element, vkey) 
------------------------------------------

**方法描述** 

在指定控件上发送快捷键

**参数说明** 

**element** *\<str\>* 控件名

**vkey** *\<str\>* 快捷键

**调用样例** - rpa.app.sap._SapSession.send_vkey-

    # 注意事项：此方法需要基于sap的session对象操作，请先通过捕捉控件功能捕捉要操作的页面元素
    # 此方法将SAP快捷键以对应的编号进行存储，鼠标悬停在方法名上可查阅对应快捷键
    # 代码调用样例如下，本例中发送的快捷键为Enter键：
    sap_session = rpa.app.sap.session(win_title="SAPXX")
    
    sap_session.send_vkey("事务代码输入框", "0")







find(element) 
-------------------------------

**方法描述** 

获取SAP原生控件句柄

**参数说明** 

**element** *\<str\>* 控件名

**调用样例** - rpa.app.sap._SapSession.find-

    # 注意事项：此方法需要基于sap的session对象操作，请先通过捕捉控件功能捕捉要操作的页面元素
    # 代码调用样例如下：
    sap_session = rpa.app.sap.session(win_title="SAPXX")
    
    raw_element = sap_session.find("执行按钮")







microsoft 
===========================

excel 
-----------------------

open(file, visible=False, readonly=False, password=None, write_password=None) 
-----------------------------------------------------------------------------------------------

**方法描述** 

打开一个Excel文件

**参数说明** 

**file** *\<str\>* 文件路径

**visible** *\<bool\>* 是否可见

**readonly** *\<bool\>* 只读

**password** *\<str\>* 文件密码

**write_password** *\<str\>* "写保护的工作簿"的密码

**返回值说明** 

返回Excel对象 *\<Excel\>* 

**调用样例** - rpa.app.microsoft.excel.open-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)







create(visible=False) 
---------------------------------------

**方法描述** 

新建Excel

**参数说明** 

**visible** *\<bool\>* 是否可见

**返回值说明** 

返回Excel对象 *\<Excel\>* 

**调用样例** - rpa.app.microsoft.excel.create-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    excel = rpa.app.microsoft.excel.create(visible=True)







catch(name, mode='filename') 
----------------------------------------------

**方法描述** 

获取已经打开的Excel文件对象

**参数说明** 

**name** *\<str\>* 文件名、文件路径

**mode** *\<str\>* 识别模式

可选项：

* filename : 文件名

  

* filepath : 文件路径

  




**返回值说明** 

返回一个Excel对象 *\<Excel\>* 

**调用样例** - rpa.app.microsoft.excel.catch-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 根据文件名获取EXCEL需要填入带扩展名的文件名
    # 代码调用样例如下：
    excel = rpa.app.microsoft.excel.catch('测试Excel.xlsx')







read(range, only_visible=False, skip=0, max=1000, read_value_as_str=True) 
-------------------------------------------------------------------------------------------

**方法描述** 

从Excel读取值

**参数说明** 

**range** *\<str\>* 'A'为列 '1'为行 'A1'为单元格 'A1:B2'为范围

**read_value_as_str** *\<bool\>* 读取内容的方式，True表示读出的内容为字符串，False表示读出的内容为其值，对于单个单元格来说，若其值为数字的均读出float，否则读出str或None。例如: excel中的单元格值为1，则读出的值为1.0

**only_visible** *\<bool\>* 只读可见

**skip** *\<int\>* 跳过多少行后开始读

**max** *\<int\>* 读列或者范围时不能超过max的范围

**调用样例** - rpa.app.microsoft.excel.Sheet.read-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    cell_value = sheet.read('A1')
    row_value = sheet.read('1')
    column_value = sheet.read('A')
    range_value = sheet.read('A1:C3')
    
    excel.close()







write(range, value, start_row=1, start_col='A', max=1000) 
---------------------------------------------------------------------------

**方法描述** 

向Excel写入数据

**参数说明** 

**range** *\<str\>* 支持列、行、单元格、范围写入，写入范围时仅填写起始单元格即可。例：'A'为列 '1'为行 'A1'为单元格

**value** *\<list\>* 当range为列/行的时候传入一维数组,写入单元格则传入str/int/float ,写入范围的时候传入二维数组

**start_row** *\<int\>* 写入列时表示从哪一行开始写 此参数仅当写入列时有效

**start_col** *\<str\>* 写入行时表示从哪一列开始写 此参数仅当写入行时有效 可传入'1'\|'A'\|'a'

**max** *\<int\>* 写入列/行/范围时不能超过max的范围

**调用样例** - rpa.app.microsoft.excel.Sheet.write-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    row_value = ["行数据1","RPA测试"]
    cell_value = "RPA单元格值"
    column_value = ["列数据1","RPA测试"]
    range_value = [["区域数据1","区域数据2"] , ["区域数据3","区域数据4"]]
    
    sheet.write('1' , row_value )
    sheet.write('C' , column_value )
    sheet.write('A2' , cell_value )
    sheet.write('A4' , range_value )
    
    excel.close()







copy(range) 
-----------------------------

**方法描述** 

复制范围内的数据

**参数说明** 

**range** *\<str\>* 'A'为列 '1'为行 'A1'为单元格 'A1:B2'为范围

**调用样例** - rpa.app.microsoft.excel.Sheet.copy-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    sheet.copy('1' )
    sheet.copy('C' )
    sheet.copy('A2' )
    sheet.copy('A4:B5' )







paste(range, paste_type='数值', retry=3) 
--------------------------------------------------------

**方法描述** 

向范围内粘贴数据

**参数说明** 

**range** *\<str\>* 粘贴目标位置，支持的格式包含行、列、粘贴范围的起始单元格，'A'为列 '1'为行 'A1'为单元格

**paste_type** *\<str\>* 数据类型

可选项：

* all : 全部

  

* formula : 公式

  

* value : 数值

  

* format : 格式

  

* annotation : 批注

  

* verification : 验证

  

* sourceUnit : 所有使用源主题的单元

  

* exceptBorder : 边框除外

  

* colWidth : 列宽

  

* FormulasNumber : 公式和数字格式

  

* valueNumber : 值和数字格式

  

* mergeCondition : 所有合并条件格式

  




**retry** *\<int\>* 重试次数

**调用样例** - rpa.app.microsoft.excel.Sheet.paste-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    sheet.copy('1' )
    sheet.paste('2')
    
    sheet.copy('C' )
    sheet.paste('D')
    
    sheet.copy('A2' )
    sheet.paste('B2')
    
    sheet.copy('A4:B5' )
    sheet.paste('C4:D5' )







row_count() 
-----------------------------

**方法描述** 

获得指定sheet的行数

**返回值说明** 

返回行数 *\<str\>* 

**调用样例** - rpa.app.microsoft.excel.Sheet.row_count-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 此方法返回的是字符串类型的数值
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    count = sheet.row_count()







col_count() 
-----------------------------

**方法描述** 

获得指定sheet的列数

**返回值说明** 

返回列数 *\<str\>* 

**调用样例** - rpa.app.microsoft.excel.Sheet.col_count-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 此方法返回的是字符串类型的数值
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    count = sheet.col_count()







sort(sort_fields, range=None, match_case=False, sort_method='pinyin', contains_header=False) 
--------------------------------------------------------------------------------------------------------------

**方法描述** 

排序

**参数说明** 

**range** *\<str\>* 查找范围: 如'A1:C5', 如果为空则查找整个Sheet(默认整个Sheet)

**sort_fileds** *\<list\>* 排序字段数组 sort_fields = \[('A', 'value', 'desc'), ('B', 'cell_color', 'asc')\]

**match_case** *\<bool\>* 是否区分大小写 默认False

**sort_method** *\<str\>* 排序方法 字母、笔划

**contains_header** *\<bool\>* 是否包含标题 默认False

**调用样例** - rpa.app.microsoft.excel.Sheet.sort-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    sort_fileds = [('A','value','desc'),('B','cell_color','asc')]
    
    sheet.sort(sort_fileds)







filter(col, array, delete=False) 
--------------------------------------------------

**方法描述** 

对列进行筛选

**参数说明** 

**col** *\<str\>* 列号

**array** *\<list\>* 筛选值数组

**delete** *\<bool\>* 筛选后是否删除，在3.4.3及以后版本无效

**调用样例** - rpa.app.microsoft.excel.Sheet.filter-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    filter_value = ['rpa_test1','rpa_test2']
    
    sheet.filter('A',filter_value)







remove_filter() 
---------------------------------

**方法描述** 

移除筛选

**调用样例** - rpa.app.microsoft.excel.Sheet.remove_filter-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    filter_value = ['rpa_test1','rpa_test2']
    
    sheet.filter('A',filter_value)
    sheet.remove_filter()







multi_filter(filters_val, range=None, delete=False) 
---------------------------------------------------------------------

**方法描述** 

对多列进行筛选

**参数说明** 

**filters_val** *\<dic\>* 按以下格式书写 {'A':\['testA1','testA2','testA3'\],'B':\['testB1','testB2'\]'...}

**range** *\<str\>* 筛选列范围: 如'A1:C5', 如果为空则筛选整个Sheet(默认整个Sheet)

**delete** *\<bool\>* 筛选后是否删除，在3.4.3及以后版本无效

**调用样例** - rpa.app.microsoft.excel.Sheet.multi_filter-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下，运行后，会开启筛选并选择A列值为test01或test02且B列值为1或2的行：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    filter_exp = {
        'A':['test01','test02'],
        'B':['1','2']
    }
    sheet.multi_filter(filter_exp)







run_macro(macro_name, file=None) 
--------------------------------------------------

**方法描述** 

运行宏

**参数说明** 

**file** *\<str\>* 宏文件路径

**macro_name** *\<str\>* 宏命令名称

**调用样例** - rpa.app.microsoft.excel.Sheet.run_macro-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 此方法仅适用于启用宏的excel文件，文件后缀一般为.xlsm
    # 代码调用样例如下，本例中的"宏1"用于取消表中所有筛选，可通过excel录制宏功能生成：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsm"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    filter_exp = {
        'A':['test01','test02'],
        'B':['1','2']
    }
    sheet.multi_filter(filter_exp)
    
    sheet.run_macro('宏1')







merge_cell(range, each_row=False) 
---------------------------------------------------

**方法描述** 

合并单元格

**参数说明** 

**range** *\<str\>* 需要合并的范围，必须为 A1:B2的格式

**each_row** *\<bool\>* 是否行内合并

**调用样例** - rpa.app.microsoft.excel.Sheet.merge_cell-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 此方法通过each_row参数指定合并形式，默认为False，将把指定区域合并为一个完整的单元格
    # 若指定each_row = True，则将把指定区域按行合并，每一行作为一个单元格
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    sheet.merge_cell('A1:B2',each_row=True)







insert(range, insertDirection=None) 
-----------------------------------------------------

**方法描述** 

插入功能

**参数说明** 

**range** *\<str\>* 'A'为列 '1'为行 'A1'为单元格 'A1:B2'为范围

**insertDirection** *\<str\>* 插入方向

可选项：

* down : 下移

  

* right : 右移

  




**调用样例** - rpa.app.microsoft.excel.Sheet.insert-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 此方法通过insertDirection参数指定插入后相邻值的移动方向，支持下移和右移
    # 代码调用样例如下，会向A1单元格插入一个空的单元格，原有数据默认下移：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    sheet.insert('A1')







delete(range, insertDirection=None) 
-----------------------------------------------------

**方法描述** 

删除功能

**参数说明** 

**range** *\<str\>* 'A'为列 '1'为行 'A1'为单元格 'A1:B2'为范围

**insertDirection** *\<str\>* 插入方向

可选项：

* up : 上移

  

* left : 左移

  




**调用样例** - rpa.app.microsoft.excel.Sheet.delete-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下，会删除A1单元格，原有数据默认上移：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    sheet.delete('A1')









remove_duplicated_cols(range, cols) 
-----------------------------------------------------

**方法描述** 

列去重功能

**参数说明** 

**range** *\<str\>* 'A'为列 'A1:B2'为范围

**cols** *\<list\>* 去重列号的列表

**调用样例** - rpa.app.microsoft.excel.Sheet.remove_duplicated_cols-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 去重列字段不能超过去重范围，如去重范围为A1:C3，则去重列字段只能从A,B,C三个中选取任意个
    # 代码调用样例如下，此例中指定了在A1:C9区域进行去重操作，一行数据上三个值均相等时，才视为重复值：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    sheet.remove_duplicated_cols('A1:C9',['A,B,C'])







create_pivot_table(data_sheet, data_range, pivot_sheet, pivot_range, pivot_settings) 
------------------------------------------------------------------------------------------------------

**方法描述** 

创建透视表

**参数说明** 

**data_sheet** *\<str\>* 透视表源数据所在Sheet名称，如'Sheet1'

**data_range** *\<str\>* 透视表源数据范围，如'A1:C10'

**pivot_sheet** *\<str\>* 透视表插入的Sheet名称，如'Sheet2'

**pivot_range** *\<str\>* 透视表插入的位置，如'A1'

**pivot_settings** *\<PivotTableSettings\>* 透视表设置

**调用样例** - rpa.app.microsoft.excel.Sheet.create_pivot_table-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下，此例中将以日期为筛选条件，以"购买者"作为行标题，以"类型"作为列标题，将"金额"进行求和计算
    # 最终得到按日期筛选，每个购买者每种类型的总成交金额统计透视表：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet('消费数据')
    
    pivot_settings = rpa.app.microsoft.excel.PivotTableSettings('数据透视表设置')
    pivot_settings.filters['日期'] = {} # 添加"筛选字段"
    pivot_settings.rows['购买者'] = {} # 添加"行标签"
    pivot_settings.columns['类型'] = {} # 添加"列标签"
    pivot_settings.values['金额'] = {"Function": "xlSum"} # 添加"数值"
    
    sheet.create_pivot_table('消费数据','A:D','数据透视表','A1',pivot_settings)
    
    excel.save()
    excel.close()



**说明** 

此例中的pivot_setings.values用于设定透视表字段值处理形式，其中Function可选的内容如下表所示：

\|--------------\|--------\|\| **Function** \| **说明** \|\| xlSum \| 求和 \|\| xlCount \| 计数 \|\| xlAverage \| 平均值 \|\| xlMax \| 最大值 \|\| xlMin \| 最小值 \|\| xlProduct \| 乘积 \|\| xlCountNums \| 数值计数 \|\| xlStDev \| 标准偏差 \|\| xlStDevP \| 总体标准偏差 \|\| xlVar \| 方差 \|\| xlVarP \| 总体方差 \|





refresh_pivot_table(index=1) 
----------------------------------------------

**方法描述** 

刷新透视表

**参数说明** 

**index** *\<int\>* 数据透视表编号,如果有多张透视表需指定第几张

**调用样例** - rpa.app.microsoft.excel.Sheet.refresh_pivot_table-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下，此例会根据数据源更新数据透视表的值：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet('数据透视表')
    
    sheet.refresh_pivot_table(index=1)







get_all_pivot_field_items(name, index=1) 
----------------------------------------------------------

**方法描述** 

获取透视表筛选列的所有项

**参数说明** 

**index** *\<int\>* 数据透视表编号,如果有多张透视表需指定第几张

**name** *\<str\>* 字段名

**返回值说明** 

返回筛选结果 *\<list\>* 

**调用样例** - rpa.app.microsoft.excel.Sheet.get_all_pivot_field_items-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下，本例会获取数据透视表中"购买者"这个字段下所有的不重复的值：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet('数据透视表')
    
    options_of_field = sheet.get_all_pivot_field_items('购买者')







select_pivot_field_items(name, array, index=1, select=True) 
-----------------------------------------------------------------------------

**方法描述** 

选择/取消选择一组透视表筛选项

**参数说明** 

**index** *\<int\>* 数据透视表编号,如果有多张透视表需指定第几张

**name** *\<str\>* 字段名

**array** *\<list\>* 待选择的值列表

**select** *\<bool\>* 选择或取消

**调用样例** - rpa.app.microsoft.excel.Sheet.select_pivot_field_items-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下，此例中会取消勾选"购买者"这个字段下，值为"AA"或"BB"的相关数据，对应数据不显现：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet('数据透视表')
    
    sheet.select_pivot_field_items('购买者',['AA','BB'],select=False)







find(text, range=None, count=0) 
-------------------------------------------------

**方法描述** 

查询

**参数说明** 

**text** *\<str\>* 要查询的内容

**range** *\<str\>* 查找范围: 如'A1:C5', 如果为空则查找整个Sheet(默认整个Sheet)

**count** *\<int\>* 0表示查找所有匹配项(默认为0)

**返回值说明** 

返回值: 二维数组，每行都是一个返回结果，第一列是行号，第二列是列号，第三列是匹配的单元格值; 返回0表示未找到任何匹配项 *\<list\>* 

**调用样例** - rpa.app.microsoft.excel.Sheet.find-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 可通过制定count参数来设定匹配项数量，默认为0，即返回所有匹配结果，设为1则按从左到右，从上到下的顺序返回第一个匹配的单元格
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    result = sheet.find('AA',count=1)







add_picture(file, col, row, width=None, height=None) 
----------------------------------------------------------------------

**方法描述** 

向指定位置插入图片

**参数说明** 

**file** *\<str\>* 插入图片的路径

**col** *\<str\>* 左上角单元格的列号

**row** *\<str\>* 左上角单元格的行号

**width** *\<str\>* 图片的宽度

**height** *\<str\>* 图片的高度

**调用样例** - rpa.app.microsoft.excel.Sheet.add_picture-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    pic_path = r'D:\2_测试文件归档\OCR文字识别.png'
    sheet.add_picture(pic_path,'C','2')







get_row_height(row) 
-------------------------------------

**方法描述** 

获得指定行高度

**参数说明** 

**row** *\<str\>* 行号

**返回值说明** 

返回行高 *\<str\>* 

**调用样例** - rpa.app.microsoft.excel.Sheet.get_row_height-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    row_height = sheet.get_row_height('1')







set_row_height(row, height) 
---------------------------------------------

**方法描述** 

设置指定行高度

**参数说明** 

**row** *\<str\>* 行号

**height** *\<str\>* 行高

**调用样例** - rpa.app.microsoft.excel.Sheet.set_row_height-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    sheet.set_row_height('1','20')







get_col_width(col) 
------------------------------------

**方法描述** 

获得指定列宽度

**参数说明** 

**col** *\<str\>* 列号

**返回值说明** 

返回列宽 *\<str\>* 

**调用样例** - rpa.app.microsoft.excel.Sheet.get_col_width-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    col_width = sheet.get_col_width('A')







set_col_width(col, width) 
-------------------------------------------

**方法描述** 

设置指定列宽度

**参数说明** 

**col** *\<str\>* 列号

**width** *\<str\>* 列宽

**调用样例** - rpa.app.microsoft.excel.Sheet.set_col_width-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    sheet.set_col_width('A','20')







get_formula(range) 
------------------------------------

**方法描述** 

获取指定范围的公式

**参数说明** 

**range** *\<str\>* 'A'为列 '1'为行 'A1'为单元格 'A1:B2'为范围

**返回值说明** 

返回指定范围的公式 *\<str\>* 

**调用样例** - rpa.app.microsoft.excel.Sheet.get_formula-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 如果操作的单元格中无公式，则将返回单元格原本的值（空或原始字符）
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    formula = sheet.get_formula("A1")







set_formula(range, formula) 
---------------------------------------------

**方法描述** 

设置指定范围的公式

**参数说明** 

**range** *\<str\>* 'A'为列 '1'为行 'A1'为单元格 'A1:B2'为范围

**formula** *\<str\>* 公式

**调用样例** - rpa.app.microsoft.excel.Sheet.set_formula-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    formula = "=TODAY()"
    sheet.set_formula("E2:F3",formula)







get_style(range, style, color_format='RGB') 
-------------------------------------------------------------

**方法描述** 

获取指定范围的样式

**参数说明** 

**range** *\<str\>* 'A'为列 '1'为行 'A1'为单元格 'A1:B2'为范围

**style** *\<str\>* 样式

可选项：

* fontsize : 字体大小

  

* fontcolor : 字体颜色

  

* fontname : 字体名称

  

* bgcolor : 背景色

  




**color_format** *\<str\>* 颜色类型，当style为fontcolor/bgcolor时有效 可传入'HEX'\|'RGB'

**调用样例** - rpa.app.microsoft.excel.Sheet.get_style-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    style = sheet.get_style("A1:B2","fontsize")



**说明** 

style参数可选值为：fontsize、fontcolor、fontname、bgcolor，分别对应字体大小、字体颜色、字体名、背景颜色。

color_format参数可选值为：HEX、RGB，分别对应十六进制颜色颜色号，形如#FFFFFF,或者RGB颜色号，形如RGB(255,255,255）



set_style(range, style, value, color_format='RGB') 
--------------------------------------------------------------------

**方法描述** 

设置指定范围的样式

**参数说明** 

**range** *\<str\>* 'A'为列 '1'为行 'A1'为单元格 'A1:B2'为范围

**style** *\<str\>* 样式

可选项：

* fontsize : 字体大小

  

* fontcolor : 字体颜色

  

* fontname : 字体名称

  

* bgcolor : 背景色

  




**value** *\<str\>* 设置该属性的值，如果style为fontcolor/bgcolor，则value可以为'#FFFFFF'或者'255,255,255'

**color_format** *\<str\>* 颜色类型，如果style为fontcolor/bgcolor，需设置format为'HEX'或者'RGB'

**调用样例** - rpa.app.microsoft.excel.Sheet.set_style-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    sheet.set_style("A2","bgcolor","RGB(0,255,0)")
    sheet.set_style("A3","bgcolor","#FF0000","HEX")







get_comment(range) 
------------------------------------

**方法描述** 

获取单元格的注释

**参数说明** 

**range** *\<str\>* 'A1'为单元格

**返回值说明** 

返回单元格的注释，当单元格没有注释时，返回None *\<str\>* 

**调用样例** - rpa.app.microsoft.excel.Sheet.get_comment-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 当目标单元格本身并无注释时，此方法将返回None
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    comment = sheet.get_comment("A1")







set_comment(range, comment) 
---------------------------------------------

**方法描述** 

往单元格插入注释

**参数说明** 

**range** *\<str\>* 'A1'为单元格

**comment** *\<str\>* 注释

**调用样例** - rpa.app.microsoft.excel.Sheet.set_comment-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    comment = "RPA测试"
    sheet.set_comment("A1",comment)







replace(text, replacement, range=None, match_case=False) 
--------------------------------------------------------------------------

**方法描述** 

替换

**参数说明** 

**text** *\<str\>* 要替换的内容

**replacement** *\<str\>* 替换成的内容

**range** *\<str\>* 查找范围: 如'A1:C5', 如果为空则查找整个Sheet(默认整个Sheet)

**match_case** *\<bool\>* 是否大小写匹配

**调用样例** - rpa.app.microsoft.excel.Sheet.replace-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 如果对应sheet上，待替换的字符不存在，程序将不执行任何动作
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    sheet.replace("test","RPA_TEST")







to_pdf(file) 
------------------------------

**方法描述** 

转化成pdf

**参数说明** 

**file** *\<str\>* 保存的pdf路径

**调用样例** - rpa.app.microsoft.excel.Sheet.to_pdf-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    path = r"D:\2_测试文件归档\sheet转pdf.pdf"
    sheet.to_pdf(path)







activate() 
----------------------------

**方法描述** 

激活当前sheet

**调用样例** - rpa.app.microsoft.excel.Sheet.activate-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 使用此方法并保存excel后，对应sheet页面会作为默认打开页，即启动对应excel文件后，对应sheet页会作为首页
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet("非默认页")
    
    sheet.active()
    
    excel.close()







set_number_format(range, format) 
--------------------------------------------------

**方法描述** 

设置指定范围的数值格式

**参数说明** 

**range** *\<str\>* 'A'为列 '1'为行 'A1'为单元格 'A1:B2'为范围

**format** *\<str\>* 如'@'，参见Excel中的单元格格式的自定义

**调用样例** - rpa.app.microsoft.excel.Sheet.set_number_format-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    sheet.set_number_format("D2","0.00")



**说明** 

format参数可选值请参考excel中的标准写法（单元格设置-数字-自定义）



save(file=None) 
---------------------------------

**方法描述** 

保存或者另存当前Excel文件，当不输入另存路径的时候就是保存当前已打开的Excel

**参数说明** 

**file** *\<str\>* 另存为的文件路径

**调用样例** - rpa.app.microsoft.excel.Sheet.Excel.save-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 进行保存操作并不会关闭Excel进程
    # 如果excel文件为新建的，则进行save操作时必须指定路径。
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    
    path = r"D:\2_测试文件归档\测试Excel-副本.xlsx"
    excel.save()
    excel.save(file=path)







close(save=True) 
----------------------------------

**方法描述** 

关闭Excel

**参数说明** 

**save** *\<bool\>* 默认保存

**调用样例** - rpa.app.microsoft.excel.Sheet.Excel.close-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 执行关闭动作默认自动保存excel，如果是新建excel，建议先通过save方法指定保存路径保存文件。
    # 建议只要涉及excel操作的，在代码末行均加上close方法，否则可能出现excel重复打开产生只读状态而无法正常处理excel的现象。
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    
    excel.close()







get_sheets() 
------------------------------

**方法描述** 

获得Excel所有的sheet列表

**返回值说明** 

返回sheet列表 *\<list\>* 

**调用样例** - rpa.app.microsoft.excel.Sheet.Excel.get_sheets-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    
    sheets = excel.get_sheets()







add_sheet(sheet_name, location, relative='before') 
--------------------------------------------------------------------

**方法描述** 

新增sheet

**参数说明** 

**sheet_name** *\<str\>* sheet名称

**location** *\<str\>* 定位插入位置的sheet的名称

**relative** *\<str\>* 对于目标sheet的方向

可选项：

* before : 前

  

* after : 后

  




**返回值说明** 

返回sheet对象 *\<Sheet\>* 

**调用样例** - rpa.app.microsoft.excel.Sheet.Excel.add_sheet-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    
    new_sheet_name = "RPA-新建表"
    excel.add_sheet(new_sheet_name ,"Sheet1")







get_sheet(sheet_name=None) 
--------------------------------------------

**方法描述** 

获取指定sheet

**参数说明** 

**sheet_name** *\<str\>* sheet名称

**返回值说明** 

返回指定Sheet，不传入时返回默认sheet *\<Sheet\>* 

**调用样例** - rpa.app.microsoft.excel.Sheet.Excel.get_sheet-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    
    sheet1 = excel.get_sheet("Sheet1")







remove_sheet(sheet_name) 
------------------------------------------

**方法描述** 

删除sheet

**参数说明** 

**sheet_name** *\<str\>* sheet名称

**调用样例** - rpa.app.microsoft.excel.Sheet.Excel.remove_sheet-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    
    excel.remove_sheet("Sheet2")







rename_sheet(old_sheet_name, new_sheet_name) 
--------------------------------------------------------------

**方法描述** 

重命名sheet

**参数说明** 

**old_sheet_name** *\<str\>* 原sheet名称

**new_sheet_name** *\<str\>* 重命名后的sheet名称

**调用样例** - rpa.app.microsoft.excel.Sheet.Excel.rename_sheet-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.microsoft.excel.open(excel_file_path,visible=True)
    
    new_name = "表格改名"
    excel.rename_sheet("Sheet1",new_name)







word 
----------------------

open(file, visible=False) 
-------------------------------------------

**方法描述** 

打开word文档

**参数说明** 

**file** *\<str\>* 文件路径

**visible** *\<bool\>* 是否可见

**返回值说明** 

返回Word文档 *\<Word\>* 

**调用样例** - rpa.app.microsoft.word.open-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.microsoft.word.open(word_file_path, visible=True)







create(visible=False) 
---------------------------------------

**方法描述** 

创建word文档

**参数说明** 

**visible** *\<bool\>* 是否可见

**返回值说明** 

返回Word文档 *\<Word\>* 

**调用样例** - rpa.app.microsoft.word.create-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    word = rpa.app.microsoft.word.create(visible=True)









row_count() 
-----------------------------

**方法描述** 

获取表格的行数

**返回值说明** 

返回行数 *\<int\>* 

**调用样例** - rpa.app.microsoft.word.Table.row_count-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.microsoft.word.open(word_file_path, visible=True)
    table = word.get_table(1)
    
    row_count = table.row_count()









col_count() 
-----------------------------

**方法描述** 

获取表格的列数

**返回值说明** 

返回列数 *\<int\>* 

**调用样例** - rpa.app.microsoft.word.Table.col_count-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.microsoft.word.open(word_file_path, visible=True)
    table = word.get_table(1)
    
    col_count = table.col_count()









read(row, col) 
--------------------------------

**方法描述** 

获取指定单元格内容

**参数说明** 

**row** *\<int\>* 行的索引

**col** *\<int\>* 列的索引

**返回值说明** 

返回指定单元格内容 *\<str\>* 

**调用样例** - rpa.app.microsoft.word.Table.read-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.microsoft.word.open(word_file_path, visible=True)
    table = word.get_table(1)
    
    data = table.read(1,1)







write(row, col, text, size=8, family='微软雅黑', color=1) 
-----------------------------------------------------------------------

**方法描述** 

向指定单元格写入内容

**参数说明** 

**row** *\<int\>* 行的索引

**col** *\<int\>* 列的索引

**text** *\<str\>* 要输入的内容

**size** *\<int\>* 字体大小

**family** *\<str\>* 字体种类

**color** *\<int\>* 字体颜色编号

**调用样例** - rpa.app.microsoft.word.Table.write-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 执行写入时请确保填写的行列参数没有超过word中原表格的行列数
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.microsoft.word.open(word_file_path, visible=True)
    table = word.get_table(1)
    text = "RPA_WORD文档表格写入测试"
    
    table.write(1,1,text)









add_row() 
---------------------------

**方法描述** 

增加一个空行

**调用样例** - rpa.app.microsoft.word.Table.add_row-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 默认在表格默认新增一行
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.microsoft.word.open(word_file_path, visible=True)
    table = word.get_table(1)
    
    table.add_row()









add_col() 
---------------------------

**方法描述** 

增加一个空列

**调用样例** - rpa.app.microsoft.word.Table.add_col-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 默认在最右边新增一列
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.microsoft.word.open(word_file_path, visible=True)
    table = word.get_table(1)
    
    table.add_col()







close() 
-------------------------

**方法描述** 

关闭word

**调用样例** - rpa.app.microsoft.word.Table.Word.close-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # close方法不会自动保存，建议先使用save方法保存后，再通过close方法关闭word
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.microsoft.word.open(word_file_path, visible=True)
    
    word.save()
    word.close()







save(file=None) 
---------------------------------

**方法描述** 

保存或另存为

**参数说明** 

**file** *\<str\>* 另存为的路径

**调用样例** - rpa.app.microsoft.word.Table.Word.save-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.microsoft.word.open(word_file_path, visible=True)
    new_path = r"D:\2_测试文件归档\测试Word-副本.docx"
    
    word.save()
    word.save(file=new_path)
    
    word.close()







write(text, size=8, family='微软雅黑', color=1) 
-------------------------------------------------------------

**方法描述** 

写入内容

**参数说明** 

**text** *\<str\>* 要输入的内容

**size** *\<int\>* 字体大小

**family** *\<str\>* 字体种类

**color** *\<int\>* 字体颜色编号

**调用样例** - rpa.app.microsoft.word.Table.Word.write-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 此方法默认在文档末尾写入一行
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.microsoft.word.open(word_file_path, visible=True)
    
    text = "RPA测试Word文档写入功能"
    word.write(text)







read() 
------------------------

**方法描述** 

读取word内容

**返回值说明** 

返回读取内容 *\<str\>* 

**调用样例** - rpa.app.microsoft.word.Table.Word.read-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 若word中有表格内容，则此方法会将其读取为文本
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.microsoft.word.open(word_file_path, visible=True)
    
    text = word.read()







search(key, from_pos='start', index=1, relative='left') 
-------------------------------------------------------------------------

**方法描述** 

查找关键字并移动光标

**参数说明** 

**key** *\<str\>* 查找的关键字

**from_pos** *\<str\>* 查找方向

可选项：

* start : 开头

  

* current : 当前

  




**index** *\<int\>* 第几个匹配 默认1

**relative** *\<str\>* 光标对于关键字的方向

可选项：

* left : 左边

  

* right : 右边

  




**调用样例** - rpa.app.microsoft.word.Table.Word.search-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下，会在word文档内容中找到对应关键词并默认将光标移动到关键词左侧：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.microsoft.word.open(word_file_path, visible=True)
    
    word.search("写入")







replace(key, replacement, match_case=False, match_whole_word=False) 
-------------------------------------------------------------------------------------

**方法描述** 

替换

**参数说明** 

**key** *\<str\>* 要替换的关键词

**replacement** *\<str\>* 要替换成的结果

**match_case** *\<bool\>* 是否大小写匹配

**match_whole_word** *\<bool\>* 是否全词匹配

**调用样例** - rpa.app.microsoft.word.Table.Word.replace-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.microsoft.word.open(word_file_path, visible=True)
    
    new_text = "测试更新"
    word.replace("写入",new_text)







cursor_move(step_count, direction='right') 
------------------------------------------------------------

**方法描述** 

移动光标

**参数说明** 

**step_count** *\<int\>* 移动步数

**direction** *\<str\>* 移动方向

可选项：

* left : 左

  

* right : 右

  

* top : 上

  

* down : 下

  




**调用样例** - rpa.app.microsoft.word.Table.Word.cursor_move-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.microsoft.word.open(word_file_path, visible=True)
    
    word.cursor_move(1,direction="top")







get_table(index) 
----------------------------------

**方法描述** 

根据索引获取表格

**参数说明** 

**index** *\<int\>* 表格索引

**返回值说明** 

返回表格对象 *\<Table\>* 

**调用样例** - rpa.app.microsoft.word.Table.Word.get_table-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.microsoft.word.open(word_file_path, visible=True)
    
    table = word.get_table(1)







add_picture(file) 
-----------------------------------

**方法描述** 

插入图片

**参数说明** 

**file** *\<str\>* 图片路径

**调用样例** - rpa.app.microsoft.word.Table.Word.add_picture-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 此方法将在当前光标位置插入图片
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.microsoft.word.open(word_file_path, visible=True)
    
    pic_path = r"D:\2_测试文件归档\测试图片.png"
    word.add_picture(pic_path )







to_pdf(file) 
------------------------------

**方法描述** 

转化成pdf

**参数说明** 

**file** *\<str\>* 保存的pdf路径

**调用样例** - rpa.app.microsoft.word.Table.Word.to_pdf-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.microsoft.word.open(word_file_path, visible=True)
    
    pdf_path = r"D:\2_测试文件归档\word文档.pdf"
    word.to_pdf(pdf_path)







get_table_content_by_keys(keys, combine=False) 
----------------------------------------------------------------

**方法描述** 

根据前后关键字获得表格的内容

**参数说明** 

**keys** *\<list\>* 关键字组合 格式为\[(start1,end1),(start2,end2)\]

**combine** *\<bool\>* 是否需要合并单元格 默认false

**返回值说明** 

返回一个二维数组 *\<list\>* 

**调用样例** - rpa.app.microsoft.word.Table.Word.get_table_content_by_keys-

    # 注意事项：使用前需确认已安装MicroSoft相关软件
    # 此方法是取两个关键词所在的自然段之间包含的第一张表格的内容，并非按照表格里的关键词进行匹配
    # 代码调用样例如下，本例中，word文档内，在一行输入文本标题"表格1"之后，插入了一张表格，然后另起一行，输入了文本标题"表格2"：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.microsoft.word.open(word_file_path, visible=True)
    
    keys = [("表格1","表格2")]
    tables = word.get_table_content_by_keys(keys)







wps 
=====================

excel 
-----------------------

open(file, visible=False, readonly=False, password=None, write_password=None, dispatch='wps') 
---------------------------------------------------------------------------------------------------------------

**方法描述** 

打开一个Excel文件

**参数说明** 

**file** *\<str\>* 文件路径

**visible** *\<bool\>* 是否可见

**readonly** *\<bool\>* 只读

**password** *\<str\>* 文件密码

**write_password** *\<str\>* "写保护的工作簿"的密码

**dispatch** *\<str\>* 使用office或wps打开

**返回值说明** 

返回Excel对象 *\<Excel\>* 

**调用样例** - rpa.app.wps.excel.open-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)







create(visible=False, dispatch='wps') 
-------------------------------------------------------

**方法描述** 

新建Excel

**参数说明** 

**visible** *\<bool\>* 是否可见

**dispatch** *\<str\>* 使用office或wps打开

**返回值说明** 

返回Excel对象 *\<Excel\>* 

**调用样例** - rpa.app.wps.excel.create-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel = rpa.app.wps.excel.create(visible=True)







read(range, only_visible=False, skip=0, max=1000) 
-------------------------------------------------------------------

**方法描述** 

从Excel读取数据，数字的返回均为float，例如: excel中的单元格值为1，则读出的值为1.0

**参数说明** 

**range** *\<str\>* 'A'为列 '1'为行 'A1'为单元格 'A1:B2'为范围

**only_visible** *\<bool\>* 只读可见

**skip** *\<int\>* 跳过多少行后开始读

**max** *\<int\>* 读列或者范围时，行数不能超过max的范围

**调用样例** - rpa.app.wps.excel.Sheet.read-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    cell_value = sheet.read('A1')
    row_value = sheet.read('1')
    column_value = sheet.read('A')
    range_value = sheet.read('A1:C3')
    
    excel.close()







write(range, value, start_row=1, start_col='A', max=1000) 
---------------------------------------------------------------------------

**方法描述** 

向Excel写入数据

**参数说明** 

**range** *\<str\>* 支持行、列、单元格、范围写入，写入范围时仅填写起始单元格即可。例：'A'为列 '1'为行 'A1'为单元格

**value** *\<list\>* 当range为列/行的时候传入一维数组,写入单元格则传入str/int/float ,写入范围的时候传入二维数组

**start_row** *\<int\>* 写入列时表示从哪一行开始写 此参数仅当写入列时有效

**start_col** *\<str\>* 写入行时表示从哪一列开始写 此参数仅当写入行时有效 可传入'1'\|'A'\|'a'

**max** *\<int\>* 写入列时不能超过max的范围

**调用样例** - rpa.app.wps.excel.Sheet.write-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    row_value = ["行数据1","RPA测试"]
    cell_value = "RPA单元格值"
    column_value = ["列数据1","RPA测试"]
    range_value = [["区域数据1","区域数据2"] , ["区域数据3","区域数据4"]]
    
    sheet.write('1' , row_value )
    sheet.write('C' , column_value )
    sheet.write('A2' , cell_value )
    sheet.write('A4' , range_value )
    
    excel.close()







copy(range) 
-----------------------------

**方法描述** 

复制范围内的数据

**参数说明** 

**range** *\<str\>* 'A'为列 '1'为行 'A1'为单元格 'A1:B2'为范围

**调用样例** - rpa.app.wps.excel.Sheet.copy-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    sheet.copy('1' )
    sheet.copy('C' )
    sheet.copy('A2' )
    sheet.copy('A4:B5' )







paste(range, paste_type='数值', retry=3) 
--------------------------------------------------------

**方法描述** 

向范围内粘贴数据

**参数说明** 

**range** *\<str\>* 粘贴目标位置，支持的格式包含行、列、粘贴范围的起始单元格，'A'为列 '1'为行 'A1'为单元格

**paste_type** *\<str\>* 数据类型

可选项：

* all : 全部

  

* formula : 公式

  

* value : 数值

  

* format : 格式

  

* annotation : 批注

  

* verification : 验证

  

* sourceUnit : 所有使用源主题的单元

  

* exceptBorder : 边框除外

  

* colWidth : 列宽

  

* FormulasNumber : 公式和数字格式

  

* valueNumber : 值和数字格式

  

* mergeCondition : 所有合并条件格式

  




**retry** *\<int\>* 重试次数

**调用样例** - rpa.app.wps.excel.Sheet.paste-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    sheet.copy('1' )
    sheet.paste('2')
    
    sheet.copy('C' )
    sheet.paste('D')
    
    sheet.copy('A2' )
    sheet.paste('B2')
    
    sheet.copy('A4:B5' )
    sheet.paste('C4:D5' )







row_count() 
-----------------------------

**方法描述** 

获得指定sheet的行数

**返回值说明** 

返回行数 *\<str\>* 

**调用样例** - rpa.app.wps.excel.Sheet.row_count-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    count = sheet.row_count()







col_count() 
-----------------------------

**方法描述** 

获得指定sheet的列数

**返回值说明** 

返回列数 *\<str\>* 

**调用样例** - rpa.app.wps.excel.Sheet.col_count-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    count = sheet.col_count()







sort(sort_fields, range=None, match_case=False, sort_method='pinyin', contains_header=False) 
--------------------------------------------------------------------------------------------------------------

**方法描述** 

排序

**参数说明** 

**range** *\<str\>* 查找范围: 如'A1:C5', 如果为空则查找整个Sheet(默认整个Sheet)

**sort_fileds** *\<list\>* 排序字段数组 sort_fields = \[('A', 'value', 'desc'), ('B', 'cellColor', 'asc')\]

**match_case** *\<bool\>* 是否区分大小写 默认False

**sort_method** *\<str\>* 排序方法 字母、笔划

**contains_header** *\<bool\>* 是否包含标题 默认False

**调用样例** - rpa.app.wps.excel.Sheet.sort-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    sort_fileds = [('A','value','desc'),('B','cell_color','asc')]
    
    sheet.sort(sort_fileds)







filter(col, array, delete=False) 
--------------------------------------------------

**方法描述** 

对列进行筛选

**参数说明** 

**col** *\<str\>* 列号

**array** *\<list\>* 筛选值数组

**delete** *\<bool\>* 筛选后是否删除，在3.4.3及以后版本无效

**调用样例** - rpa.app.wps.excel.Sheet.filter-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    filter_value = ['rpa_test1','rpa_test2']
    
    sheet.filter('A',filter_value)







remove_filter() 
---------------------------------

**方法描述** 

移除筛选

**调用样例** - rpa.app.wps.excel.Sheet.remove_filter-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    filter_value = ['rpa_test1','rpa_test2']
    
    sheet.filter('A',filter_value)
    sheet.remove_filter()







merge_cell(range, each_row=False) 
---------------------------------------------------

**方法描述** 

合并单元格

**参数说明** 

**range** *\<str\>* 需要合并的范围，必须为 A1:B2的格式

**each_row** *\<bool\>* 是否行内合并

**调用样例** - rpa.app.wps.excel.Sheet.merge_cell-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 此方法通过each_row参数指定合并形式，默认为False，将把指定区域合并为一个完整的单元格
    # 若指定each_row = True，则将把指定区域按行合并，每一行作为一个单元格
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    sheet.merge_cell('A1:B2',each_row=True)







insert(range, insertDirection=None) 
-----------------------------------------------------

**方法描述** 

插入功能

**参数说明** 

**range** *\<str\>* 'A'为列 '1'为行 'A1'为单元格 'A1:B2'为范围

**insertDirection** *\<str\>* 插入方向

可选项：

* down : 下移

  

* right : 右移

  




**调用样例** - rpa.app.wps.excel.Sheet.insert-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 此方法通过insertDirection参数指定插入后相邻值的移动方向，支持下移和右移
    # 代码调用样例如下，会向A1单元格插入一个空的单元格，原有数据默认下移：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    sheet.insert('A1')







delete(range, insertDirection=None) 
-----------------------------------------------------

**方法描述** 

删除功能

**参数说明** 

**range** *\<str\>* 'A'为列 '1'为行 'A1'为单元格 'A1:B2'为范围

**insertDirection** *\<str\>* 插入方向

可选项：

* up : 上移

  

* left : 左移

  




**调用样例** - rpa.app.wps.excel.Sheet.delete-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下，会删除A1单元格，原有数据默认上移：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    sheet.delete('A1')







remove_duplicated_cols(range, cols) 
-----------------------------------------------------

**方法描述** 

列去重功能

**参数说明** 

**range** *\<str\>* 'A'为列 'A1:B2'为范围

**cols** *\<list\>* 去重列号的列表

**调用样例** - rpa.app.wps.excel.Sheet.remove_duplicated_cols-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 去重列字段不能超过去重范围，如去重范围为A1:C3，则去重列字段只能从A,B,C三个中选取任意个
    # 代码调用样例如下，此例中指定了在A1:C9区域进行去重操作，一行数据上三个值均相等时，才视为重复值：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    sheet.remove_duplicated_cols('A1:C9',['A,B,C'])







find(text, range=None, count=0) 
-------------------------------------------------

**方法描述** 

查询

**参数说明** 

**text** *\<str\>* 要查询的内容

**range** *\<str\>* 查找范围: 如'A1:C5', 如果为空则查找整个Sheet(默认整个Sheet)

**count** *\<int\>* 0表示查找所有匹配项(默认为0)

**返回值说明** 

返回值: 二维数组，每行都是一个返回结果，第一列是行号，第二列是列号，第三列是匹配的单元格值; 返回0表示未找到任何匹配项 *\<list\>* 

**调用样例** - rpa.app.wps.excel.Sheet.find-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 可通过制定count参数来设定匹配项数量，默认为0，即返回所有匹配结果，设为1则按从左到右，从上到下的顺序返回第一个匹配的单元格
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    result = sheet.find('AA',count=1)







add_picture(file, col, row, width=None, height=None) 
----------------------------------------------------------------------

**方法描述** 

向指定位置插入图片

**参数说明** 

**file** *\<str\>* 插入图片的路径

**col** *\<str\>* 左上角单元格的列号

**row** *\<str\>* 左上角单元格的行号

**width** *\<float\>* 图片的宽度

**height** *\<float\>* 图片的高度

**调用样例** - rpa.app.wps.excel.Sheet.add_picture-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    pic_path = r'D:\2_测试文件归档\OCR文字识别.png'
    sheet.add_picture(pic_path,'C','2')







get_row_height(row) 
-------------------------------------

**方法描述** 

获得指定行高度

**参数说明** 

**row** *\<str\>* 行号

**返回值说明** 

返回行高 *\<str\>* 

**调用样例** - rpa.app.wps.excel.Sheet.get_row_height-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    row_height = sheet.get_row_height('1')







set_row_height(row, height) 
---------------------------------------------

**方法描述** 

设置指定行高度

**参数说明** 

**row** *\<str\>* 行号

**height** *\<str\>* 行高

**调用样例** - rpa.app.wps.excel.Sheet.set_row_height-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    sheet.set_row_height('1','20')







get_col_width(col) 
------------------------------------

**方法描述** 

获得指定列宽度

**参数说明** 

**col** *\<str\>* 列号

**返回值说明** 

返回列宽 *\<str\>* 

**调用样例** - rpa.app.wps.excel.Sheet.get_col_width-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    col_width = sheet.get_col_width('A')







set_col_width(col, width) 
-------------------------------------------

**方法描述** 

设置指定列宽度

**参数说明** 

**col** *\<str\>* 列号

**width** *\<str\>* 列宽

**调用样例** - rpa.app.wps.excel.Sheet.set_col_width-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    sheet.set_col_width('A','20')







get_formula(range) 
------------------------------------

**方法描述** 

获取指定范围的公式

**参数说明** 

**range** *\<str\>* 'A'为列 '1'为行 'A1'为单元格 'A1:B2'为范围

**返回值说明** 

返回指定范围的公式 *\<str\>* 

**调用样例** - rpa.app.wps.excel.Sheet.get_formula-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    formula = sheet.get_formula("A1")







set_formula(range, formula) 
---------------------------------------------

**方法描述** 

设置指定范围的公式

**参数说明** 

**range** *\<str\>* 'A'为列 '1'为行 'A1'为单元格 'A1:B2'为范围

**formula** *\<str\>* 公式

**调用样例** - rpa.app.wps.excel.Sheet.set_formula-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    formula = "=TODAY()"
    sheet.set_formula("E2:F3",formula)







get_style(range, style, color_format='RGB') 
-------------------------------------------------------------

**方法描述** 

获取指定范围的样式

**参数说明** 

**range** *\<str\>* 'A'为列 '1'为行 'A1'为单元格 'A1:B2'为范围

**style** *\<str\>* 样式

可选项：

* fontsize : 字体大小

  

* fontcolor : 字体颜色

  

* fontname : 字体名称

  

* bgcolor : 背景色

  




**color_format** *\<str\>* 颜色类型，当style为fontcolor/bgcolor时有效 可传入'HEX'\|'RGB'

**调用样例** - rpa.app.wps.excel.Sheet.get_style-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    style = sheet.get_style("A1:B2","fontsize")







set_style(range, style, value, color_format='RGB') 
--------------------------------------------------------------------

**方法描述** 

设置指定范围的样式

**参数说明** 

**range** *\<str\>* 'A'为列 '1'为行 'A1'为单元格 'A1:B2'为范围

**style** *\<str\>* 样式

可选项：

* fontsize : 字体大小

  

* fontcolor : 字体颜色

  

* fontname : 字体名称

  

* bgcolor : 背景色

  




**value** *\<str\>* 设置该属性的值，如果style为fontcolor/bgcolor，则value可以为'#FFFFFF'或者'255,255,255'

**format** *\<str\>* 颜色类型，如果style为fontcolor/bgcolor，需设置format为'HEX'或者'RGB'

**调用样例** - rpa.app.wps.excel.Sheet.set_style-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    sheet.set_style("A3","bgcolor","#FF0000","HEX")







get_comment(range) 
------------------------------------

**方法描述** 

获取单元格的注释

**参数说明** 

**range** *\<str\>* 'A1'为单元格

**返回值说明** 

返回单元格的注释，当单元格没有注释时，返回None *\<str\>* 

**调用样例** - rpa.app.wps.excel.Sheet.get_comment-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 当目标单元格本身并无注释时，此方法将返回None
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    comment = sheet.get_comment("A1")







set_comment(range, comment) 
---------------------------------------------

**方法描述** 

往单元格插入注释

**参数说明** 

**range** *\<str\>* 'A1'为单元格

**comment** *\<str\>* 注释

**调用样例** - rpa.app.wps.excel.Sheet.set_comment-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    comment = "RPA测试"
    sheet.set_comment("A1",comment)







replace(text, replacement, range=None, match_case=False) 
--------------------------------------------------------------------------

**方法描述** 

替换

**参数说明** 

**text** *\<str\>* 要替换的内容

**replacement** *\<str\>* 替换成的内容

**range** *\<str\>* 查找范围: 如'A1:C5', 如果为空则查找整个Sheet(默认整个Sheet)

**match_case** *\<bool\>* 是否大小写匹配

**调用样例** - rpa.app.wps.excel.Sheet.replace-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    sheet.replace("test","RPA_TEST")







to_pdf(file) 
------------------------------

**方法描述** 

转化成pdf

**参数说明** 

**file** *\<str\>* 保存的pdf路径

**调用样例** - rpa.app.wps.excel.Sheet.to_pdf-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    sheet = excel.get_sheet()
    
    path = r"D:\2_测试文件归档\sheet转pdf.pdf"
    sheet.to_pdf(path)







save(file=None) 
---------------------------------

**方法描述** 

保存或者另存当前Excel文件，当不输入另存路径的时候就是保存当前已打开的Excel

**参数说明** 

**file** *\<str\>* 另存为的文件路径

**调用样例** - rpa.app.wps.excel.Sheet.Excel.save-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 进行保存操作并不会关闭Excel进程
    # 如果excel文件为新建的，则进行save操作时必须指定路径
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    
    path = r"D:\2_测试文件归档\测试Excel-副本.xlsx"
    excel.save()
    excel.save(file=path)







close(save=True) 
----------------------------------

**方法描述** 

关闭Excel

**参数说明** 

**save** *\<bool\>* 默认保存

**调用样例** - rpa.app.wps.excel.Sheet.Excel.close-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    
    excel.close()







get_sheets() 
------------------------------

**方法描述** 

获得Excel所有的sheet列表

**返回值说明** 

返回sheet列表 *\<list\>* 

**调用样例** - rpa.app.wps.excel.Sheet.Excel.get_sheets-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    
    sheets = excel.get_sheets()







add_sheet(sheet_name, location, relative='before') 
--------------------------------------------------------------------

**方法描述** 

新增sheet

**参数说明** 

**sheet_name** *\<str\>* sheet名称

**location** *\<str\>* 定位插入位置的sheet的名称

**relative** *\<str\>* 对于目标sheet的方向

可选项：

* before : 前

  

* after : 后

  




**返回值说明** 

返回sheet对象 *\<Sheet\>* 

**调用样例** - rpa.app.wps.excel.Sheet.Excel.add_sheet-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    
    new_sheet_name = "RPA-新建表"
    excel.add_sheet(new_sheet_name ,"Sheet1")







get_sheet(sheet_name=None) 
--------------------------------------------

**方法描述** 

获取指定sheet

**返回值说明** 

返回指定Sheet，不传入时返回默认sheet *\<Sheet\>* 

**调用样例** - rpa.app.wps.excel.Sheet.Excel.get_sheet-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    
    sheet1 = excel.get_sheet("Sheet1")







remove_sheet(sheet_name) 
------------------------------------------

**方法描述** 

删除sheet

**参数说明** 

**sheet_name** *\<str\>* sheet名称

**调用样例** - rpa.app.wps.excel.Sheet.Excel.remove_sheet-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    
    excel.remove_sheet("Sheet2")







rename_sheet(old_sheet_name, new_sheet_name) 
--------------------------------------------------------------

**方法描述** 

重命名sheet

**参数说明** 

**old_sheet_name** *\<str\>* 原sheet名称

**new_sheet_name** *\<str\>* 重命名后的sheet名称

**调用样例** - rpa.app.wps.excel.Sheet.Excel.rename_sheet-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsx"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    
    new_name = "表格改名"
    excel.rename_sheet("Sheet1",new_name)







run_macro(macro_name, file=None) 
--------------------------------------------------

**方法描述** 

运行宏

**参数说明** 

**file** *\<str\>* 宏文件路径

**macro_name** *\<str\>* 宏命令名称

**调用样例** - rpa.app.wps.excel.Sheet.Excel.run_macro-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    excel_file_path = r"D:\2_测试文件归档\测试Excel.xlsm"
    excel = rpa.app.wps.excel.open(excel_file_path,visible=True)
    
    excel.run_macro("宏1")







word 
----------------------

open(file, visible=False, dispatch='wps') 
-----------------------------------------------------------

**方法描述** 

打开word文档

**参数说明** 

**file** *\<str\>* 文件路径

**visible** *\<bool\>* 是否可见

**dispatch** *\<str\>* 使用office或wps打开

**返回值说明** 

返回Word文档 *\<Word\>* 

**调用样例** - rpa.app.wps.word.open-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.wps.word.open(word_file_path, visible=True)







create(visible=False, dispatch='wps') 
-------------------------------------------------------

**方法描述** 

创建word文档

**参数说明** 

**visible** *\<bool\>* 是否可见

**dispatch** *\<str\>* 使用office或wps打开

**返回值说明** 

返回Word文档 *\<Word\>* 

**调用样例** - rpa.app.wps.word.create-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    word = rpa.app.wps.word.create(visible=True)







row_count() 
-----------------------------

**方法描述** 

获取表格的行数

**返回值说明** 

返回行数 *\<int\>* 

**调用样例** - rpa.app.wps.word.Table.row_count-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.wps.word.open(word_file_path, visible=True)
    table = word.get_table(1)
    
    row_count = table.row_count()







col_count() 
-----------------------------

**方法描述** 

获取表格的列数

**返回值说明** 

返回列数 *\<int\>* 

**调用样例** - rpa.app.wps.word.Table.col_count-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.wps.word.open(word_file_path, visible=True)
    table = word.get_table(1)
    
    col_count = table.col_count()







read(row, col) 
--------------------------------

**方法描述** 

获取指定单元格内容

**参数说明** 

**row** *\<int\>* 行的索引

**col** *\<int\>* 列的索引

**返回值说明** 

返回指定单元格内容 *\<str\>* 

**调用样例** - rpa.app.wps.word.Table.read-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.wps.word.open(word_file_path, visible=True)
    table = word.get_table(1)
    
    data = table.read(1,1)







write(row, col, text, size=8, family='微软雅黑', color=1) 
-----------------------------------------------------------------------

**方法描述** 

向指定单元格写入内容

**参数说明** 

**row** *\<int\>* 行的索引

**col** *\<int\>* 列的索引

**text** *\<str\>* 要输入的内容

**size** *\<int\>* 字体大小

**family** *\<str\>* 字体种类

**color** *\<int\>* 字体颜色编号

**调用样例** - rpa.app.wps.word.Table.write-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.wps.word.open(word_file_path, visible=True)
    table = word.get_table(1)
    text = "RPA_WORD文档表格写入测试"
    
    table.write(1,1,text)







add_row() 
---------------------------

**方法描述** 

增加一个空行

**调用样例** - rpa.app.wps.word.Table.add_row-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.wps.word.open(word_file_path, visible=True)
    table = word.get_table(1)
    
    table.add_row()







add_col() 
---------------------------

**方法描述** 

增加一个空列

**调用样例** - rpa.app.wps.word.Table.add_col-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.wps.word.open(word_file_path, visible=True)
    table = word.get_table(1)
    
    table.add_col()







close() 
-------------------------

**方法描述** 

关闭word

**调用样例** - rpa.app.wps.word.Table.Word.close-

    # 注意事项：使用前需确认已安装WPS相关软件
    # close方法不会自动保存，建议先使用save方法保存后，再通过close方法关闭word
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.wps.word.open(word_file_path, visible=True)
    
    word.save()
    word.close()







save(file=None) 
---------------------------------

**方法描述** 

保存或另存为

**参数说明** 

**file** *\<str\>* 另存为的路径

**调用样例** - rpa.app.wps.word.Table.Word.save-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.wps.word.open(word_file_path, visible=True)
    new_path = r"D:\2_测试文件归档\测试Word-副本.docx"
    
    word.save()
    word.save(file=new_path)
    
    word.close()







write(text, size=8, family='微软雅黑', color=1) 
-------------------------------------------------------------

**方法描述** 

写入内容

**参数说明** 

**text** *\<str\>* 要输入的内容

**size** *\<int\>* 字体大小

**family** *\<str\>* 字体种类

**color** *\<str\>* 字体颜色编号

**调用样例** - rpa.app.wps.word.Table.Word.write-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.wps.word.open(word_file_path, visible=True)
    
    text = "RPA测试Word文档写入功能"
    word.write(text)







read() 
------------------------

**方法描述** 

读取word内容

**返回值说明** 

返回读取内容 *\<str\>* 

**调用样例** - rpa.app.wps.word.Table.Word.read-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.wps.word.open(word_file_path, visible=True)
    
    text = word.read()







search(key, from_pos='start', index=1, relative='left') 
-------------------------------------------------------------------------

**方法描述** 

查找关键字并移动光标

**参数说明** 

**key** *\<str\>* 查找的关键字

**from_pos** *\<str\>* 查找方向

可选项：

* start : 开头

  

* current : 当前

  




**index** *\<int\>* 第几个匹配 默认1

**relative** *\<str\>* 光标对于关键字的方向

可选项：

* left : 左边

  

* right : 右边

  




**调用样例** - rpa.app.wps.word.Table.Word.search-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下，会在word文档内容中找到对应关键词并默认将光标移动到关键词左侧：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.wps.word.open(word_file_path, visible=True)
    
    word.search("写入")







replace(key, replacement, match_case=False, match_whole_word=False) 
-------------------------------------------------------------------------------------

**方法描述** 

替换

**参数说明** 

**key** *\<str\>* 要替换的关键词

**replacement** *\<str\>* 要替换成的结果

**match_case** *\<bool\>* 是否大小写匹配

**match_whole_word** *\<bool\>* 是否全词匹配

**调用样例** - rpa.app.wps.word.Table.Word.replace-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.wps.word.open(word_file_path, visible=True)
    
    new_text = "测试更新"
    word.replace("写入",new_text)







cursor_move(step_count, direction='right') 
------------------------------------------------------------

**方法描述** 

移动光标

**参数说明** 

**step_count** *\<int\>* 移动步数

**direction** *\<str\>* 移动方向

可选项：

* left : 左

  

* right : 右

  

* top : 上

  

* down : 下

  




**调用样例** - rpa.app.wps.word.Table.Word.cursor_move-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.wps.word.open(word_file_path, visible=True)
    
    word.cursor_move(1,direction="top")







get_table(index) 
----------------------------------

**方法描述** 

根据索引获取表格

**参数说明** 

**index** *\<int\>* 表格索引

**返回值说明** 

返回表格对象 *\<Table\>* 

**调用样例** - rpa.app.wps.word.Table.Word.get_table-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.wps.word.open(word_file_path, visible=True)
    
    table = word.get_table(1)







add_picture(file) 
-----------------------------------

**方法描述** 

插入图片

**参数说明** 

**file** *\<str\>* 图片路径

**调用样例** - rpa.app.wps.word.Table.Word.add_picture-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 此方法将在当前光标位置插入图片
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.wps.word.open(word_file_path, visible=True)
    
    pic_path = r"D:\2_测试文件归档\测试图片.png"
    word.add_picture(pic_path )







to_pdf(file) 
------------------------------

**方法描述** 

转化成pdf

**参数说明** 

**file** *\<str\>* 保存的pdf路径

**调用样例** - rpa.app.wps.word.Table.Word.to_pdf-

    # 注意事项：使用前需确认已安装WPS相关软件
    # 代码调用样例如下：
    word_file_path = r"D:\2_测试文件归档\测试Word.docx"
    word = rpa.app.wps.word.open(word_file_path, visible=True)
    
    pdf_path = r"D:\2_测试文件归档\word文档.pdf"
    word.to_pdf(pdf_path)







