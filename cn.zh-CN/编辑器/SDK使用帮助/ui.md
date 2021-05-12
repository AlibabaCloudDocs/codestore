ui 
=======================

本文档主要介绍编辑器组件面板中UI Automation目录下相关组件的使用。

win32 
=======================

catch(title, mode='start', process_name=None, class_name=None, timeout=10) 
--------------------------------------------------------------------------------------------

**方法描述** 

根据标题捕获窗口对象

**参数说明** 

**title** *\<str\>* 窗口标题

**mode** *\<str\>* 窗口匹配模式

可选项：

* start : 头匹配

  

* substr : 包含

  

* exact : 完全匹配

  

* reg : 正则表达式匹配

  




**process_name** *\<str\>* 进程名称

**class_name** *\<str\>* 窗口类名

**timeout** *\<int\>* 等待窗口超时时间 单位秒

**返回值说明** 

返回窗口对象 *\<Window\>* 

**调用样例** - rpa.ui.win32.catch-

    # 注意事项：使用此方法需要确保对应程序窗口已打开
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch('钉钉',mode='exact',process_name='DingTalk')







click(x=None, y=None, button='left') 
------------------------------------------------------

**方法描述** 

鼠标点击

**参数说明** 

**button** *\<str\>* 鼠标键位

可选项：

* left : 左键

  

* right : 右键

  




**调用样例** - rpa.ui.win32.click-

    # 注意事项：无
    # 代码调用样例如下：
    rpa.ui.win32.click(x=500,y=500,button='left')







double_click(x=None, y=None) 
----------------------------------------------

**方法描述** 

鼠标双击

**调用样例** - rpa.ui.win32.double_click-

    # 注意事项：无
    # 代码调用样例如下：
    rpa.ui.win32.double_click(x=500,y=500)









drive_input(value, replace=True, wait_mili_seconds=20, timeout=10) 
------------------------------------------------------------------------------------

**方法描述** 

以驱动输入的方式直接输入文本

**参数说明** 

**value** *\<str\>* 输入的内容

**replace** *\<bool\>* 是否清空之前的内容

**wait_mili_seconds** *\<int\>* 字符间输入间隔（毫秒），仅在模拟输入下有效，默认值为20，最大值100，该值设置过大可能会引起超时

**timeout** *\<int\>* 等待控件超时时间

**调用样例** - rpa.ui.win32.drive_input-

    # 注意事项：驱动输入需要以管理员权限执行，应用涉及驱动输入时，请使用管理员身份打开编辑器及机器人
    # 代码调用样例如下：
    rpa.ui.win32.drive_input("test")









double_click(x=None, y=None) 
----------------------------------------------

**方法描述** 

鼠标双击

**调用样例** - rpa.ui.win32.double_click-

    # 注意事项：无
    # 代码调用样例如下：
    rpa.ui.win32.double_click(x=500,y=500)









mouse_move(x, y) 
----------------------------------

**方法描述** 

鼠标移动

**调用样例** - rpa.ui.win32.mouse_move-

    # 注意事项：无
    # 代码调用样例如下：
    rpa.ui.win32.mouse_move(500,500)









capture(file, x1, y1, x2, y2) 
-----------------------------------------------

**方法描述** 

屏幕截图

**调用样例** - rpa.ui.win32.capture-

    # 注意事项：无
    # 代码调用样例如下：
    path =  r'D:\2_测试文件归档\屏幕截图.jpg'
    rpa.ui.win32.capture(path,0,0,500,500)







send_key(key) 
-------------------------------

**方法描述** 

发送按键

**参数说明** 

**key** *\<str\>* 按键内容

**调用样例** - rpa.ui.win32.send_key-

    # 注意事项：无
    # 代码调用样例如下，本例中会向记事本窗口发送按键文本：
    wnd = rpa.ui.win32.catch('test.txt - 记事本')
    wnd.activate()
    ​
    rpa.ui.win32.send_key("TEST")







win_activate(title, mode='start') 
---------------------------------------------------

**方法描述** 

窗口激活

**参数说明** 

**title** *\<str\>* 窗口标题

**mode** *\<str\>* 窗口匹配模式

可选项：

* start : 头匹配

  

* substr : 包含

  

* exact : 完全匹配

  

* reg : 正则表达式匹配

  




**调用样例** - rpa.ui.win32.win_activate-

    # 注意事项：使用此方法需要确认存在对应窗口进程
    # 代码调用样例如下，此例中会将记事本窗口激活置顶：
    rpa.ui.win32.win_activate("test.txt - 记事本")







win_maximize(title, mode='start') 
---------------------------------------------------

**方法描述** 

窗口最大化

**参数说明** 

**title** *\<str\>* 窗口标题

**mode** *\<str\>* 窗口匹配模式

可选项：

* start : 头匹配

  

* substr : 包含

  

* exact : 完全匹配

  

* reg : 正则表达式匹配

  




**调用样例** - rpa.ui.win32.win_maximize-

    # 注意事项：使用此方法需要确认存在对应窗口进程
    # 代码调用样例如下，此例中会将记事本窗口最大化：
    rpa.ui.win32.win_minimize("test.txt - 记事本")







win_minimize(title, mode='start') 
---------------------------------------------------

**方法描述** 

窗口最小化

**参数说明** 

**title** *\<str\>* 窗口标题

**mode** *\<str\>* 窗口匹配模式

可选项：

* start : 头匹配

  

* substr : 包含

  

* exact : 完全匹配

  

* reg : 正则表达式匹配

  




**调用样例** - rpa.ui.win32.win_minimize-

    # 注意事项：使用此方法需要确认存在对应窗口进程
    # 代码调用样例如下，此例中会将记事本窗口最小化：
    rpa.ui.win32.win_minimize("test.txt - 记事本")







win_hide(title, mode='start') 
-----------------------------------------------

**方法描述** 

窗口隐藏

**参数说明** 

**title** *\<str\>* 窗口标题

**mode** *\<str\>* 窗口匹配模式

可选项：

* start : 头匹配

  

* substr : 包含

  

* exact : 完全匹配

  

* reg : 正则表达式匹配

  




**调用样例** - rpa.ui.win32.win_hide-

    # 注意事项：此方法会将窗口从任务栏移除，之后仅能在任务管理器进程中查看到
    # 代码调用样例如下：
    rpa.ui.win32.win_hide("test.txt - 记事本")







win_show(title, mode='start') 
-----------------------------------------------

**方法描述** 

窗口显示

**参数说明** 

**title** *\<str\>* 窗口标题

**mode** *\<str\>* 窗口匹配模式

可选项：

* start : 头匹配

  

* substr : 包含

  

* exact : 完全匹配

  

* reg : 正则表达式匹配

  




**调用样例** - rpa.ui.win32.win_show-

    # 注意事项：无
    # 代码调用样例如下：
    rpa.ui.win32.win_show("test.txt - 记事本")







win_exists(title, mode='start') 
-------------------------------------------------

**方法描述** 

窗口是否存在

**参数说明** 

**title** *\<str\>* 窗口标题

**mode** *\<str\>* 窗口匹配模式

可选项：

* start : 头匹配

  

* substr : 包含

  

* exact : 完全匹配

  

* reg : 正则表达式匹配

  




**返回值说明** 

返回窗口是否存在 *\<bool\>* 

**调用样例** - rpa.ui.win32.win_exists-

    # 注意事项：无
    # 代码调用样例如下：
    exist_flag = rpa.ui.win32.win_exists("test.txt - 记事本")







win_close(title, mode='start') 
------------------------------------------------

**方法描述** 

窗口关闭

**参数说明** 

**title** *\<str\>* 窗口标题

**mode** *\<str\>* 窗口匹配模式

可选项：

* start : 头匹配

  

* substr : 包含

  

* exact : 完全匹配

  

* reg : 正则表达式匹配

  




**调用样例** - rpa.ui.win32.win_close-

    # 注意事项：无
    # 代码调用样例如下：
    rpa.ui.win32.win_close("test.txt - 记事本")







win_wait_appear(title, timeout=30) 
----------------------------------------------------

**方法描述** 

等待窗口出现

**参数说明** 

**title** *\<str\>* 窗口标题

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.ui.win32.win_wait_appear-

    # 注意事项：无
    # 代码调用样例如下：
    rpa.ui.win32.win_wait_appear("test.txt - 记事本",timeout=10)







win_wait_disappear(title, timeout=30) 
-------------------------------------------------------

**方法描述** 

等待窗口消失

**参数说明** 

**title** *\<str\>* 窗口标题

**timeout** *\<int\>* 超时时间 单位秒

**调用样例** - rpa.ui.win32.win_wait_disappear-

    # 注意事项：无
    # 代码调用样例如下：
    rpa.ui.win32.win_wait_disappear("test.txt - 记事本",timeout=10)







elem_input_text(element, value, index=1, parent_element=None, simulate=True, replace=True, send_window_message=True, sent_raw=False, wait_mili_seconds=20, timeout=10) 
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**方法描述** 

向控件输入文本

**参数说明** 

**element** *\<str\>* 控件名

**value** *\<str\>* 输入的内容

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**simulate** *\<bool\>* 是否模拟输入

**replace** *\<bool\>* 是否清空之前的内容

**send_window_message** *\<bool\>* 是否发送Windows消息

**sent_raw** *\<bool\>* 是否发送原始按键

**wait_mili_seconds** *\<int\>* 字符间输入间隔（毫秒），仅在模拟输入下有效，默认值为20，最大值100，该值设置过大可能会引起超时

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.win32.elem_input_text-

    # 注意事项：
    # 使用此方法前需通过捕捉控件功能捕捉要操作的界面元素
    # 此方法执行时，需确认对应窗口已打开（窗口标题要与捕捉控件时控件对应的窗口标题一致）
    # 代码调用样例如下：
    text = "RPA_测试"
    rpa.ui.win32.elem_input_text("记事本输入区",text)







elem_input_hotkeys(element, value, index=1, parent_element=None, timeout=10) 
----------------------------------------------------------------------------------------------

**方法描述** 

向控件输入快捷键

**参数说明** 

**element** *\<str\>* 控件名

**value** *\<str\>* 输入的内容

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.win32.elem_input_hotkeys-

    # 注意事项：
    # 使用此方法前需通过捕捉控件功能捕捉要操作的界面元素
    # 此方法执行时，需确认对应窗口已打开（窗口标题要与捕捉控件时控件对应的窗口标题一致）
    # 虚拟键写法请参考：https://www.yuque.com/aliyun_rpa/quzm63/vk
    # 代码调用样例如下：
    rpa.ui.win32.elem_input_hotkeys("记事本输入区","VK_RETURN")









elem_drive_input(element, value, index=1, replace=True, parent_element=None, wait_mili_seconds=20, timeout=10) 
--------------------------------------------------------------------------------------------------------------------------------

**方法描述** 

以驱动输入的方式向控件中输入文本

**参数说明** 

**element** *\<str\>* 控件名

**value** *\<str\>* 输入的内容

**index** *\<int\>* 如果有多个，给出控件下标

**replace** *\<bool\>* 是否清空之前的内容

**parent_element** *\<Element\>* 父控件对象

**wait_mili_seconds** *\<int\>* 字符间输入间隔（毫秒），仅在模拟输入下有效，默认值为20，最大值100，该值设置过大可能会引起超时

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.win32.elem_drive_input-

    # 注意事项：驱动输入需要以管理员权限执行，应用涉及驱动输入时，请使用管理员身份打开编辑器及机器人
    # 使用此方法前需通过捕捉控件功能捕捉要操作的界面元素
    # 此方法执行时，需确认对应窗口已打开（窗口标题要与捕捉控件时控件对应的窗口标题一致）
    # 代码调用样例如下：
    rpa.ui.win32.elem_drive_input("记事本输入区","TEST")







elem_click(element, index=1, simulate=True, button='left', parent_element=None, timeout=10) 
-------------------------------------------------------------------------------------------------------------

**方法描述** 

点击控件

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**simulate** *\<bool\>* 是否模拟点击

**button** *\<str\>* 鼠标键位

可选项：

* left : 左键

  

* right : 右键

  




**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.win32.elem_click-

    # 注意事项：
    # 使用此方法前需通过捕捉控件功能捕捉要操作的界面元素
    # 此方法执行时，需确认对应窗口已打开（窗口标题要与捕捉控件时控件对应的窗口标题一致）
    # 代码调用样例如下：
    rpa.ui.win32.elem_click("记事本输入区")







elem_get_checked_state(element, index=1, parent_element=None, timeout=10) 
-------------------------------------------------------------------------------------------

**方法描述** 

获取复选框状态

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回复选框的状态 *\<bool\>* 

**调用样例** - rpa.ui.win32.elem_get_checked_state-

    # 注意事项：
    # 使用此方法前需通过捕捉控件功能捕捉要操作的界面元素
    # 此方法执行时，需确认对应窗口已打开（窗口标题要与捕捉控件时控件对应的窗口标题一致）
    # 代码调用样例如下：
    flag = rpa.ui.win32.elem_get_checked_state("复选框")







elem_set_checked_state(element, value=True, index=1, parent_element=None, timeout=10) 
-------------------------------------------------------------------------------------------------------

**方法描述** 

设置复选框状态

**参数说明** 

**element** *\<str\>* 控件名

**value** *\<bool\>* 传入True则勾选，传入False取消勾选

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.win32.elem_set_checked_state-

    # 注意事项：
    # 使用此方法前需通过捕捉控件功能捕捉要操作的界面元素
    # 此方法执行时，需确认对应窗口已打开（窗口标题要与捕捉控件时控件对应的窗口标题一致）
    # 代码调用样例如下：
    rpa.ui.win32.elem_set_checked_state("复选框",value=False)







elem_text(element, index=1, parent_element=None, timeout=10) 
------------------------------------------------------------------------------

**方法描述** 

获取控件中的文本

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回文本 *\<str\>* 

**调用样例** - rpa.ui.win32.elem_text-

    # 注意事项：
    # 使用此方法前需通过捕捉控件功能捕捉要操作的界面元素
    # 此方法执行时，需确认对应窗口已打开（窗口标题要与捕捉控件时控件对应的窗口标题一致）
    # 代码调用样例如下：
    rpa.ui.win32.elem_text("标题栏")







get_element_by_name(element, index=1, parent_element=None, timeout=10) 
----------------------------------------------------------------------------------------

**方法描述** 

根据控件名获取控件对象

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回控件对象 *\<Element\>* 

**调用样例** - rpa.ui.win32.get_element_by_name-

    # 注意事项：无
    # 代码调用样例如下：
    element = rpa.ui.win32.get_element_by_name("记事本输入区")







elem_count(element, parent_element=None, timeout=10) 
----------------------------------------------------------------------

**方法描述** 

获取控件个数

**参数说明** 

**element** *\<str\>* 控件名

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回控件个数 *\<int\>* 

**调用样例** - rpa.ui.win32.elem_count-

    # 注意事项：
    # 使用此方法前需通过捕捉控件功能捕捉要操作的界面元素
    # 此方法执行时，需确认对应窗口已打开（窗口标题要与捕捉控件时控件对应的窗口标题一致）
    # 代码调用样例如下：
    count = rpa.ui.win32.elem_count("复选框")







elem_wait_loaded(element, index=1, timeout=10) 
----------------------------------------------------------------

**方法描述** 

等待加载控件，成功返回True，失败返回False

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回是否加载成功 *\<bool\>* 

**调用样例** - rpa.ui.win32.elem_wait_loaded-

    # 注意事项：使用此方法时，如果超过timeout设定的时间仍未定位到对应控件，则返回False
    # 代码调用样例如下：
    flag = rpa.ui.win32.elem_wait_loaded("记事本输入区")







elem_double_click(element, index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------------------

**方法描述** 

双击控件

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.win32.elem_double_click-

    # 使用此方法前需通过捕捉控件功能捕捉要操作的界面元素
    # 此方法执行时，需确认对应窗口已打开（窗口标题要与捕捉控件时控件对应的窗口标题一致）
    # 代码调用样例如下：
    rpa.ui.win32.elem_double_click("记事本输入区")







elem_mouse_move(element, index=1, timeout=10) 
---------------------------------------------------------------

**方法描述** 

鼠标移入控件

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.win32.elem_mouse_move-

    # 使用此方法前需通过捕捉控件功能捕捉要操作的界面元素
    # 此方法执行时，需确认对应窗口已打开（窗口标题要与捕捉控件时控件对应的窗口标题一致）
    # 代码调用样例如下，此例中鼠标会移入到记事本编辑区中心位置：
    rpa.ui.win32.elem_mouse_move("记事本输入区")







elem_pos(element, index=1, timeout=10) 
--------------------------------------------------------

**方法描述** 

获取控件的坐标

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回坐标{x1,y1,x2,y2} *\<dict\>* 

**调用样例** - rpa.ui.win32.elem_pos-

    # 使用此方法前需通过捕捉控件功能捕捉要操作的界面元素
    # 此方法执行时，需确认对应窗口已打开（窗口标题要与捕捉控件时控件对应的窗口标题一致）
    # 代码调用样例如下：
    pos_dict = rpa.ui.win32.elem_pos("记事本输入区")







elem_get_selected_items(element, mode='all', index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------------------------------------

**方法描述** 

获取combobox的所有选项或者所有选中的选项

**参数说明** 

**element** *\<str\>* 控件名

**mode** *\<str\>* 选择模式

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回选项的数组 *\<list\>* 

**调用样例** - rpa.ui.win32.elem_get_selected_items-

    # 使用此方法前需通过捕捉控件功能捕捉要操作的界面元素
    # 此方法执行时，需确认对应窗口已打开（窗口标题要与捕捉控件时控件对应的窗口标题一致）
    # 代码调用样例如下：
    option_list = rpa.ui.win32.elem_get_selected_items("combox选项框")







elem_set_selected_item_by_text(element, text, index=1, parent_element=None, timeout=10) 
---------------------------------------------------------------------------------------------------------

**方法描述** 

combobox--根据指定文本选中下拉列表中的项

**参数说明** 

**element** *\<str\>* 控件名

**text** *\<str\>* 选项文本

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.win32.elem_set_selected_item_by_text-

    # 使用此方法前需通过捕捉控件功能捕捉要操作的界面元素
    # 此方法执行时，需确认对应窗口已打开（窗口标题要与捕捉控件时控件对应的窗口标题一致）
    # 代码调用样例如下：
    rpa.ui.win32.elem_set_selected_item_by_text("combox选项框","选项1")







elem_get_datetimepicker(element, index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------------------------

**方法描述** 

获取日期控件时间

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回日期控件时间\[年,月,日,时,分,秒\] *\<list\>* 

**调用样例** - rpa.ui.win32.elem_get_datetimepicker-

    # 使用此方法前需通过捕捉控件功能捕捉要操作的界面元素
    # 此方法执行时，需确认对应窗口已打开（窗口标题要与捕捉控件时控件对应的窗口标题一致）
    # 代码调用样例如下：
    rpa.ui.win32.elem_get_datetimepicker("标准日期控件")







elem_set_datetimepicker(element, year=1970, month=1, day=1, hour=0, minute=0, second=0, index=1, parent_element=None, timeout=10) 
---------------------------------------------------------------------------------------------------------------------------------------------------

**方法描述** 

设置日期控件时间

**参数说明** 

**element** *\<str\>* 控件名

**year** *\<int\>* 年

**month** *\<int\>* 月

**day** *\<int\>* 日

**hour** *\<int\>* 时

**minute** *\<int\>* 分

**second** *\<int\>* 秒

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.win32.elem_set_datetimepicker-

    # 使用此方法前需通过捕捉控件功能捕捉要操作的界面元素
    # 此方法执行时，需确认对应窗口已打开（窗口标题要与捕捉控件时控件对应的窗口标题一致）
    # 代码调用样例如下：
    rpa.ui.win32.elem_set_datetimepicker("标准日期控件",year=2021,month=5,day=1,hour=0,minute=0,second=0)







save_file_dialog(path, title='保存文件') 
------------------------------------------------------

**方法描述** 

打开保存文件弹框

**参数说明** 

**path** *\<str\>* 文件保存路径

**title** *\<str\>* 窗口标题(正则匹配) 默认'保存文件'

**调用样例** - rpa.ui.win32.save_file_dialog-

    # 使用此方法前需通过捕捉控件功能捕捉要操作的界面元素
    # 此方法执行时，需确认对应窗口已打开（窗口标题要与捕捉控件时控件对应的窗口标题一致）
    # 代码调用样例如下：
    path = r"D:\2_测试文件归档\文件下载测试.txt"
    rpa.ui.win32.elem_click("下载按钮")
    ​
    rpa.ui.win32.save_file_dialog(path,title='保存文件')







open_file_dialog(path, title='打开文件') 
------------------------------------------------------

**方法描述** 

打开上传文件弹框

**参数说明** 

**path** *\<str\>* 文件保存路径

**title** *\<str\>* 窗口标题(正则匹配) 默认'打开文件'

**调用样例** - rpa.ui.win32.open_file_dialog-

    # 使用此方法前需通过捕捉控件功能捕捉要操作的界面元素
    # 此方法执行时，需确认对应窗口已打开（窗口标题要与捕捉控件时控件对应的窗口标题一致）
    # 代码调用样例如下：
    path = r"D:\2_测试文件归档\打开文件测试.txt"
    rpa.ui.win32.elem_click("打开文件按钮")
    ​
    rpa.ui.win32.save_file_dialog(path,title='打开文件')







activate() 
----------------------------

**方法描述** 

激活窗口

**调用样例** - rpa.ui.win32.Window.activate-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    wnd.activate()







maximize() 
----------------------------

**方法描述** 

最大化窗口

**调用样例** - rpa.ui.win32.Window.maximize-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    wnd.maximize()







minimize() 
----------------------------

**方法描述** 

最小化窗口

**调用样例** - rpa.ui.win32.Window.minimize-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    wnd.minimize()







hide() 
------------------------

**方法描述** 

隐藏窗口

**调用样例** - rpa.ui.win32.Window.hide-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    wnd.hide()







show() 
------------------------

**方法描述** 

窗口显示

**调用样例** - rpa.ui.win32.Window.show-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    wnd.show()







wait_disappear(timeout=30) 
--------------------------------------------

**方法描述** 

等待窗口消失

**参数说明** 

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.ui.win32.Window.wait_disappear-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    wnd.wait_disappear()







close() 
-------------------------

**方法描述** 

关闭窗口

**调用样例** - rpa.ui.win32.Window.close-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    wnd.close()







get_element_by_name(element, index=1, parent_element=None, timeout=10) 
----------------------------------------------------------------------------------------

**方法描述** 

根据控件名获取控件对象

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回控件对象 *\<Element\>* 

**调用样例** - rpa.ui.win32.Window.get_element_by_name-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    ele = wnd.get_element_by_name("记事本输入框")







count(element, parent_element=None) 
-----------------------------------------------------

**方法描述** 

获取控件个数

**参数说明** 

**element** *\<str\>* 控件名

**parent_element** *\<Element\>* 父控件对象

**返回值说明** 

返回控件个数 *\<int\>* 

**调用样例** - rpa.ui.win32.Window.count-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    ele_count = wnd.count("记事本输入框")







wait_loaded(element, index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------------

**方法描述** 

等待加载控件，成功返回True，失败返回False

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回是否加载成功 *\<bool\>* 

**调用样例** - rpa.ui.win32.Window.wait_loaded-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    wnd.wait_loaded("记事本输入框")







input_text(element, value, index=1, parent_element=None, simulate=False, replace=True, send_window_message=True, sent_raw=False, wait_mili_seconds=20, timeout=10) 
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**方法描述** 

向控件中输入文本

**参数说明** 

**element** *\<str\>* 控件名

**value** *\<str\>* 输入的内容

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**simulate** *\<bool\>* 是否模拟输入

**replace** *\<bool\>* 是否清空之前的内容

**send_window_message** *\<bool\>* 是否发送Windows消息，仅非模拟模式有效

**sent_raw** *\<bool\>* 是否发送原始按键，仅非模拟模式有效

**wait_mili_seconds** *\<int\>* 字符间输入间隔（毫秒），仅在模拟输入下有效，默认值为20，最大值100，该值设置过大可能会引起超时

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.win32.Window.input_text-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    wnd.input_text("记事本输入框", "测试一下")







input_hotkeys(element, value, replace=False, index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------------------------------------

**方法描述** 

向控件输入快捷键

**参数说明** 

**element** *\<str\>* 控件名

**value** *\<str\>* 输入的内容

**replace** *\<bool\>* 是否清空之前的内容

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.win32.Window.input_hotkeys-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    wnd.input_hotkeys("记事本输入框", "VK_BACK")







drive_input(element, value, replace=True, index=1, parent_element=None, wait_mili_seconds=20, timeout=10) 
---------------------------------------------------------------------------------------------------------------------------

**方法描述** 

以驱动输入的方式向控件中输入文本

**参数说明** 

**element** *\<str\>* 控件名

**value** *\<str\>* 输入的内容

**replace** *\<bool\>* 是否清空之前的内容

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**wait_mili_seconds** *\<int\>* 字符间输入间隔（毫秒），仅在模拟输入下有效，默认值为20，最大值100，该值设置过大可能会引起超时

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.win32.Window.drive_input-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    wnd.drive_input("记事本输入框", "RpaTest")







click(element, button='left', simulate=True, offset_x=0, offset_y=0, index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------------------------------------------------------------

**方法描述** 

点击控件，默认点击控件中心，可通过设定偏移量点击指定位置

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**simulate** *\<bool\>* 是否模拟点击

**offset_x** *\<int\>* 横向偏移量

**offset_y** *\<int\>* 纵向偏移量

**button** *\<str\>* 鼠标键位

可选项：

* left : 左键

  

* right : 右键

  




**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.win32.Window.click-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    wnd.click("记事本输入框")







double_click(element, offset_x=0, offset_y=0, index=1, parent_element=None, simulate=True, timeout=10) 
------------------------------------------------------------------------------------------------------------------------

**方法描述** 

双击控件，默认双击控件中心，可通过设定偏移量双击指定位置

**参数说明** 

**element** *\<str\>* 控件名

**offset_x** *\<int\>* 横向偏移量

**offset_y** *\<int\>* 纵向偏移量

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**simulate** *\<bool\>* 是否模拟点击

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.win32.Window.double_click-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    wnd.double_click("记事本输入框")







expand(element, index=1, parent_element=None, timeout=10) 
---------------------------------------------------------------------------

**方法描述** 

控件展开节点

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.win32.Window.expand-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    wnd.expand("控件名称")







collapse(element, index=1, parent_element=None, timeout=10) 
-----------------------------------------------------------------------------

**方法描述** 

控件折叠节点

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间

**调用样例** - rpa.ui.win32.Window.collapse-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    wnd.collapse("控件名称")







set_selected_item_by_text(element, text, index=1, parent_element=None, timeout=10) 
----------------------------------------------------------------------------------------------------

**方法描述** 

combobox--根据指定文本选中下拉列表中的项

**参数说明** 

**element** *\<str\>* 控件名

**text** *\<str\>* 选项文本

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.win32.Window.set_selected_item_by_text-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    wnd.set_selected_item_by_text("控件名称", "选择内容")







set_selected_item_by_index(element, item_index, index=1, parent_element=None, timeout=10) 
-----------------------------------------------------------------------------------------------------------

**方法描述** 

combobox--根据指定下标选中下拉列表中的项

**参数说明** 

**element** *\<str\>* 控件名

**item_index** *\<int\>* 选项下标

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.win32.Window.set_selected_item_by_index-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    wnd.set_selected_item_by_index("控件名称", "要选择内容的序号")







get_selected_items(element, mode='selected', index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------------------------------------

**方法描述** 

获取combobox的所有选项或者所有选中的选项

**参数说明** 

**element** *\<str\>* 控件名

**mode** *\<str\>* 选择模式

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回选项的数组 *\<list\>* 

**调用样例** - rpa.ui.win32.Window.get_selected_items-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    selected_items = wnd.get_selected_items("控件名称")







set_checked_state(element, value=True, index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------------------------------

**方法描述** 

设置复选框状态

**参数说明** 

**element** *\<str\>* 控件名

**value** *\<bool\>* 是否勾选

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.win32.Window.set_checked_state-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    wnd.set_checked_state("控件名称", value=True)







get_checked_state(element, index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------------------

**方法描述** 

获取复选框状态

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回复选框的状态 *\<bool\>* 

**调用样例** - rpa.ui.win32.Window.get_checked_state-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    checked_state = wnd.get_checked_state("控件名称")







get_selected(element, index=1, parent_element=None, timeout=10) 
---------------------------------------------------------------------------------

**方法描述** 

获取选中状态

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回是否选中 *\<bool\>* 

**调用样例** - rpa.ui.win32.Window.get_selected-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    checked_state = wnd.get_selected("控件名称")







text(element, index=1, parent_element=None, timeout=10) 
-------------------------------------------------------------------------

**方法描述** 

获取控件中的文本

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回文本 *\<str\>* 

**调用样例** - rpa.ui.win32.Window.text-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    text = wnd.text("控件名称")







pos(element, index=1, parent_element=None, timeout=10) 
------------------------------------------------------------------------

**方法描述** 

获取控件的坐标

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回坐标{x1,y1,x2,y2} *\<dict\>* 

**调用样例** - rpa.ui.win32.Window.pos-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    pos = wnd.pos("控件名称")







table(element, index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------

**方法描述** 

获取控件表格内容

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回表格内容 *\<list\>* 

**调用样例** - rpa.ui.win32.Window.table-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    table_list = wnd.table("控件名称")







scroll(element, percent, direction='top', index=1, parent_element=None, timeout=10) 
-----------------------------------------------------------------------------------------------------

**方法描述** 

将滚动条滚动到指定位置（位置范围0-100）,由于windows系统底层接口问题，设置的值可能会和实际值存在正负1%的偏差

**参数说明** 

**element** *\<str\>* 控件名

**percent** *\<int/float\>* 滚动百分比

可选项：

* top : 向上滚动

  

* left : 向下滚动

  




**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.win32.Window.scroll-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    wnd.scroll("控件名称", 50)







get_horizontal_scroll_percent(element, index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------------------------------

**方法描述** 

获取横向滚动条位置（位置范围0-100）

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回横向滚动条位置 *\<float\>* 

**调用样例** - rpa.ui.win32.Window.get_horizontal_scroll_percent-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    horizontal_scroll_percent = wnd.get_horizontal_scroll_percent("控件名称")







get_vertical_scroll_percent(element, index=1, parent_element=None, timeout=10) 
------------------------------------------------------------------------------------------------

**方法描述** 

获取纵向滚动条位置（位置范围0-100）

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回纵向滚动条位置 *\<float\>* 

**调用样例** - rpa.ui.win32.Window.get_vertical_scroll_percent-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    horizontal_scroll_percent = wnd.get_vertical_scroll_percent("控件名称")







screenshot(element, file, index=1, parent_element=None, timeout=10) 
-------------------------------------------------------------------------------------

**方法描述** 

控件截图

**参数说明** 

**element** *\<str\>* 控件名

**file** *\<str\>* 保存截图完成路径(含文件名)

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.win32.Window.screenshot-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    wnd.screenshot("控件名称", "d:\1.png")







mouse_move(element, index=1, parent_element=None, timeout=10) 
-------------------------------------------------------------------------------

**方法描述** 

鼠标移入控件

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.win32.Window.mouse_move-

    # 注意事项：无
    # 代码调用样例如下：
    wnd = rpa.ui.win32.catch("记事本", mode="substr")
    wnd.mouse_move("控件名称", "d:\1.png")







java 
======================

catch(title, mode='start', process_name=None, class_name=None, timeout=10) 
--------------------------------------------------------------------------------------------

**方法描述** 

根据标题捕获窗口对象

**参数说明** 

**title** *\<str\>* 窗口标题

**mode** *\<str\>* 窗口匹配模式

可选项：

* start : 头匹配

  

* substr : 包含

  

* exact : 完全匹配

  

* reg : 正则表达式匹配

  




**process_name** *\<str\>* 进程名称

**class_name** *\<str\>* 窗口类名

**timeout** *\<int\>* 等待窗口超时时间 单位秒

**返回值说明** 

返回窗口对象 *\<JavaWindow\>* 

**调用样例** - rpa.ui.java.catch-

    # 注意事项：无
    # 代码调用样例如下：
    java_wnd = rpa.ui.java.catch("Pycharm",mode="substr")







get_element_by_name(element, index=1, parent_element=None, timeout=10) 
----------------------------------------------------------------------------------------

**方法描述** 

根据控件名获取控件对象

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回控件对象 *\<Element\>* 

**调用样例** - rpa.ui.java.get_element_by_name-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    java_elem = rpa.ui.java.get_element_by_name("JAVA控件")







elem_count(element, parent_element=None, timeout=10) 
----------------------------------------------------------------------

**方法描述** 

获取控件个数

**参数说明** 

**element** *\<str\>* 控件名

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回控件个数 *\<int\>* 

**调用样例** - rpa.ui.java.elem_count-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    count = rpa.ui.java.get_elem_count("JAVA控件")







elem_wait_loaded(element, index=1, timeout=10) 
----------------------------------------------------------------

**方法描述** 

等待加载控件，成功返回True，失败返回False

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回是否加载成功 *\<bool\>* 

**调用样例** - rpa.ui.java.elem_wait_loaded-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    flag = rpa.ui.java.elem_wait_loaded("JAVA控件")







elem_input_text(element, value, index=1, parent_element=None, simulate=True, replace=True, send_window_message=False, sent_raw=False, wait_mili_seconds=20, timeout=10) 
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**方法描述** 

向控件输入文本

**参数说明** 

**element** *\<str\>* 控件名

**value** *\<str\>* 输入的内容

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**simulate** *\<bool\>* 是否模拟输入

**replace** *\<bool\>* 是否清空之前的内容

**send_window_message** *\<bool\>* 是否发送Windows消息

**sent_raw** *\<bool\>* 是否发送原始按键

**wait_mili_seconds** *\<int\>* 字符间输入间隔（毫秒），仅在模拟输入下有效，默认值为20，最大值100，该值设置过大可能会引起超时

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.java.elem_input_text-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    rpa.ui.java.elem_input_text("JAVA控件","RPA_测试")







elem_input_hotkeys(element, value, index=1, parent_element=None, timeout=10) 
----------------------------------------------------------------------------------------------

**方法描述** 

向控件输入快捷键

**参数说明** 

**element** *\<str\>* 控件名

**value** *\<str\>* 输入的内容

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.java.elem_input_hotkeys-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    rpa.ui.java.elem_input_hotkeys("JAVA控件","VK_BACK")







elem_click(element, index=1, simulate=True, send_window_message=False, button='left', offset_x=0, offset_y=0, parent_element=None, timeout=10) 
----------------------------------------------------------------------------------------------------------------------------------------------------------------

**方法描述** 

点击控件

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**simulate** *\<bool\>* 是否模拟点击

**send_window_message** *\<bool\>* 是否发送Windows消息

**offset_x** *\<int\>* 横向偏移量

**offset_y** *\<int\>* 纵向偏移量

**button** *\<str\>* 鼠标键位

可选项：

* left : 左键

  

* right : 右键

  




**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.java.elem_click-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    rpa.ui.java.elem_click("JAVA控件")







elem_double_click(element, offset_x=0, offset_y=0, index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------------------------------------------

**方法描述** 

双击控件

**参数说明** 

**element** *\<str\>* 控件名

**offset_x** *\<int\>* 横向偏移量

**offset_y** *\<int\>* 纵向偏移量

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.java.elem_double_click-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    rpa.ui.java.elem_double_click("JAVA控件")







elem_expand(element, index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------------

**方法描述** 

控件节点展开

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.java.elem_expand-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    rpa.ui.java.elem_expand("JAVA控件")







elem_collapse(element, index=1, parent_element=None, timeout=10) 
----------------------------------------------------------------------------------

**方法描述** 

控件节点折叠

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.java.elem_collapse-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    rpa.ui.java.elem_collapse("JAVA控件")







elem_set_selected_item_by_index(element, item_index, index=1, parent_element=None, timeout=10) 
----------------------------------------------------------------------------------------------------------------

**方法描述** 

combobox--根据指定下标选中下拉列表中的项

**参数说明** 

**element** *\<str\>* 控件名

**item_index** *\<int\>* 选项下标

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.java.elem_set_selected_item_by_index-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    rpa.ui.java.elem_set_selected_item_by_index("JAVA控件",2)







elem_set_selected_item_by_text(element, text, index=1, parent_element=None, timeout=10) 
---------------------------------------------------------------------------------------------------------

**方法描述** 

combobox--根据指定文本选中下拉列表中的项

**参数说明** 

**element** *\<str\>* 控件名

**text** *\<str\>* 选项文本

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.java.elem_set_selected_item_by_text-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    rpa.ui.java.elem_set_selected_item_by_text("JAVA控件","下拉选项")







elem_get_selected_items(element, mode='all', index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------------------------------------

**方法描述** 

获取combobox的所有选项或者所有选中的选项

**参数说明** 

**element** *\<str\>* 控件名

**mode** *\<str\>* 选择模式

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回item的数组 *\<list\>* 

**调用样例** - rpa.ui.java.elem_get_selected_items-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    option_list = rpa.ui.java.elem_get_selected_items("JAVA控件")







elem_set_checked_state(element, value=True, index=1, parent_element=None, timeout=10) 
-------------------------------------------------------------------------------------------------------

**方法描述** 

设置复选框状态

**参数说明** 

**element** *\<str\>* 控件名

**value** *\<bool\>* 是否勾选

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.java.elem_set_checked_state-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    rpa.ui.java.elem_set_checked_state("JAVA控件",value=False)







elem_get_checked_state(element, index=1, parent_element=None, timeout=10) 
-------------------------------------------------------------------------------------------

**方法描述** 

获取复选框状态

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回复选框的状态 *\<bool\>* 

**调用样例** - rpa.ui.java.elem_get_checked_state-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    state = rpa.ui.java.elem_get_checked_state("JAVA控件")







get_selected(element, index=1, parent_element=None, timeout=10) 
---------------------------------------------------------------------------------

**方法描述** 

获取选中状态

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回是否选中 *\<bool\>* 

**调用样例** - rpa.ui.java.get_selected-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    selected_flag = rpa.ui.java.get_selected("JAVA控件")







elem_text(element, index=1, parent_element=None, timeout=10) 
------------------------------------------------------------------------------

**方法描述** 

获取控件中的文本

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回文本 *\<str\>* 

**调用样例** - rpa.ui.java.elem_text-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    text = rpa.ui.java.elem_text("JAVA控件")







elem_value(element, index=1, parent_element=None, timeout=10) 
-------------------------------------------------------------------------------

**方法描述** 

获取控件中的值

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回控件中的值 *\<str\>* 

**调用样例** - rpa.ui.java.elem_value-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    value = rpa.ui.java.elem_value("JAVA控件")







elem_pos(element, index=1, parent_element=None, timeout=10) 
-----------------------------------------------------------------------------

**方法描述** 

获取控件坐标

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回坐标{x1,y1,x2,y2} *\<dict\>* 

**调用样例** - rpa.ui.java.elem_pos-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    pos_dict = rpa.ui.java.elem_pos("JAVA控件")







elem_table(element, index=1, parent_element=None, timeout=10) 
-------------------------------------------------------------------------------

**方法描述** 

获取控件表格内容

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回表格内容 *\<list\>* 

**调用样例** - rpa.ui.java.elem_table-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    table_data = rpa.ui.java.elem_table("JAVA控件")







elem_screenshot(element, file, index=1, parent_element=None, timeout=10) 
------------------------------------------------------------------------------------------

**方法描述** 

控件截图

**参数说明** 

**element** *\<str\>* 控件名

**file** *\<str\>* 保存截图完成路径(含文件名)

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.java.elem_screenshot-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    path = r"D:\2_测试文件归档\java控件截图.jpg"
    rpa.ui.java.elem_screenshot("JAVA控件",path)







elem_mouse_move(element, index=1, parent_element=None, timeout=10) 
------------------------------------------------------------------------------------

**方法描述** 

鼠标移入控件

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.java.elem_mouse_move-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    rpa.ui.java.elem_mouse_move("JAVA控件")







activate() 
----------------------------

**方法描述** 

激活窗口

**调用样例** - rpa.ui.java.JavaWindow.activate-

    # 注意事项：
    # 代码调用样例如下：
    java_wnd = rpa.ui.java.catch("Pycharm",mode="substr")
    ​
    java_wnd.activate()







maximize() 
----------------------------

**方法描述** 

最大化窗口

**调用样例** - rpa.ui.java.JavaWindow.maximize-

    # 注意事项：
    # 代码调用样例如下：
    java_wnd = rpa.ui.java.catch("Pycharm",mode="substr")
    ​
    java_wnd.maximize()







minimize() 
----------------------------

**方法描述** 

最小化窗口

**调用样例** - rpa.ui.java.JavaWindow.minimize-

    # 注意事项：
    # 代码调用样例如下：
    java_wnd = rpa.ui.java.catch("Pycharm",mode="substr")
    ​
    java_wnd.minimize()







hide() 
------------------------

**方法描述** 

隐藏窗口

**调用样例** - rpa.ui.java.JavaWindow.hide-

    # 注意事项：
    # 代码调用样例如下：
    java_wnd = rpa.ui.java.catch("Pycharm",mode="substr")
    ​
    java_wnd.hide()







show() 
------------------------

**方法描述** 

窗口显示

**调用样例** - rpa.ui.java.JavaWindow.show-

    # 注意事项：
    # 代码调用样例如下：
    java_wnd = rpa.ui.java.catch("Pycharm",mode="substr")
    ​
    java_wnd.show()







wait_disappear(timeout=30) 
--------------------------------------------

**方法描述** 

等待窗口消失

**参数说明** 

**timeout** *\<int\>* 超时时间

**调用样例** - rpa.ui.java.JavaWindow.wait_disappear-

    # 注意事项：
    # 代码调用样例如下：
    java_wnd = rpa.ui.java.catch("Pycharm",mode="substr")
    ​
    java_wnd.wait_disappear(timeout=10)







close() 
-------------------------

**方法描述** 

关闭窗口

**调用样例** - rpa.ui.java.JavaWindow.close-

    # 注意事项：
    # 代码调用样例如下：
    java_wnd = rpa.ui.java.catch("Pycharm",mode="substr")
    ​
    java_wnd.close()







get_element_by_name(element, index=1, parent_element=None, timeout=10) 
----------------------------------------------------------------------------------------

**方法描述** 

获取控件对象

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回控件对象 *\<Element\>* 

**调用样例** - rpa.ui.java.JavaWindow.get_element_by_name-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    java_wnd = rpa.ui.java.catch("Pycharm",mode="substr")
    ​
    java_elem = java_wnd.get_element_by_name("JAVA控件")









count(element, parent_element=None) 
-----------------------------------------------------

**方法描述** 

获取控件个数

**参数说明** 

**element** *\<str\>* 控件名

**parent_element** *\<Element\>* 父控件对象

**返回值说明** 

返回控件个数 *\<int\>* 

**调用样例** - rpa.ui.java.JavaWindow.count-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    java_wnd = rpa.ui.java.catch("Pycharm",mode="substr")
    ​
    count = java_wnd.count("JAVA控件")







wait_loaded(element, index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------------

**方法描述** 

等待加载控件，成功返回True，失败返回False

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回是否加载成功 *\<bool\>* 

**调用样例** - rpa.ui.java.JavaWindow.wait_loaded-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    java_wnd = rpa.ui.java.catch("Pycharm",mode="substr")
    ​
    flag= java_wnd.wait_loaded("JAVA控件",timeout=5)







input_text(element, value, index=1, parent_element=None, simulate=False, replace=True, send_window_message=True, sent_raw=False, wait_mili_seconds=20, timeout=10) 
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

**方法描述** 

向控件输入文本

**参数说明** 

**element** *\<str\>* 控件名

**value** *\<str\>* 输入的内容

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**simulate** *\<bool\>* 是否模拟输入

**replace** *\<bool\>* 是否清空之前的内容

**send_window_message** *\<bool\>* 是否发送Windows消息，仅非模拟模式有效

**sent_raw** *\<bool\>* 是否发送原始按键，仅非模拟模式有效

**wait_mili_seconds** *\<int\>* 字符间输入间隔（毫秒），仅在模拟输入下有效，默认值为20，最大值100，该值设置过大可能会引起超时

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.java.JavaWindow.input_text-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    java_wnd = rpa.ui.java.catch("Pycharm",mode="substr")
    ​
    java_wnd.input_text("JAVA控件","RPA_测试")







input_hotkeys(element, value, replace=False, index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------------------------------------

**方法描述** 

向控件输入快捷键

**参数说明** 

**element** *\<str\>* 控件名

**value** *\<str\>* 输入的内容

**replace** *\<bool\>* 是否清空之前的内容

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.java.JavaWindow.input_hotkeys-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    java_wnd = rpa.ui.java.catch("Pycharm",mode="substr")
    ​
    java_wnd.input_hotkeys("JAVA控件","VK_RETURN")







click(element, button='left', simulate=True, send_window_message=False, offset_x=0, offset_y=0, index=1, parent_element=None, timeout=10) 
-----------------------------------------------------------------------------------------------------------------------------------------------------------

**方法描述** 

点击控件

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**simulate** *\<bool\>* 是否模拟点击

**send_window_message** *\<bool\>* 是否发送Windows消息，仅非模拟模式有效

**offset_x** *\<int\>* 横向偏移量

**offset_y** *\<int\>* 纵向偏移量

**button** *\<str\>* 鼠标键位

可选项：

* left : 左键

  

* right : 右键

  




**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.java.JavaWindow.click-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    java_wnd = rpa.ui.java.catch("Pycharm",mode="substr")
    ​
    java_wnd.click("JAVA控件")







double_click(element, offset_x=0, offset_y=0, index=1, parent_element=None, simulate=True, timeout=10) 
------------------------------------------------------------------------------------------------------------------------

**方法描述** 

双击控件

**参数说明** 

**element** *\<str\>* 控件名

**offset_x** *\<int\>* 横向偏移量

**offset_y** *\<int\>* 纵向偏移量

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**simulate** *\<bool\>* 是否模拟点击

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.java.JavaWindow.double_click-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    java_wnd = rpa.ui.java.catch("Pycharm",mode="substr")
    ​
    java_wnd.double_click("JAVA控件")







expand(element, index=1, parent_element=None, timeout=10) 
---------------------------------------------------------------------------

**方法描述** 

控件节点展开

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.java.JavaWindow.expand-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    java_wnd = rpa.ui.java.catch("Pycharm",mode="substr")
    ​
    java_wnd.expand("JAVA控件")







collapse(element, index=1, parent_element=None, timeout=10) 
-----------------------------------------------------------------------------

**方法描述** 

控件节点折叠

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.java.JavaWindow.collapse-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    java_wnd = rpa.ui.java.catch("Pycharm",mode="substr")
    ​
    java_wnd.collapse("JAVA控件")







set_selected_item_by_text(element, text, index=1, parent_element=None, timeout=10) 
----------------------------------------------------------------------------------------------------

**方法描述** 

combobox--根据指定文本选中下拉列表中的项

**参数说明** 

**element** *\<str\>* 控件名

**text** *\<str\>* 选项文本

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.java.JavaWindow.set_selected_item_by_text-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    java_wnd = rpa.ui.java.catch("Pycharm",mode="substr")
    ​
    java_wnd.set_selected_item_by_text("JAVA控件","下拉选项")







set_selected_item_by_index(element, item_index, index=1, parent_element=None, timeout=10) 
-----------------------------------------------------------------------------------------------------------

**方法描述** 

combobox--根据指定下标选中下拉列表中的项

**参数说明** 

**element** *\<str\>* 控件名

**item_index** *\<int\>* 选项下标

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.java.JavaWindow.set_selected_item_by_index-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    java_wnd = rpa.ui.java.catch("Pycharm",mode="substr")
    ​
    java_wnd.set_selected_item_by_index("JAVA控件","下拉选项")







get_selected_items(element, mode='selected', index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------------------------------------

**方法描述** 

获取combobox的所有选项或者所有选中的选项

**参数说明** 

**element** *\<str\>* 控件名

**mode** *\<str\>* 选择模式

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回item的数组 *\<list\>* 

**调用样例** - rpa.ui.java.JavaWindow.get_selected_items-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    java_wnd = rpa.ui.java.catch("Pycharm",mode="substr")
    ​
    option_list = java_wnd.get_selected_items("JAVA控件")







set_checked_state(element, value=True, index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------------------------------

**方法描述** 

设置复选框状态

**参数说明** 

**element** *\<str\>* 控件名

**value** *\<bool\>* 是否勾选

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.java.JavaWindow.set_checked_state-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    java_wnd = rpa.ui.java.catch("Pycharm",mode="substr")
    ​
    java_wnd.set_checked_state("JAVA控件", value=False)







get_checked_state(element, index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------------------

**方法描述** 

获取复选框状态

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回复选框的状态 *\<bool\>* 

**调用样例** - rpa.ui.java.JavaWindow.get_checked_state-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    java_wnd = rpa.ui.java.catch("Pycharm",mode="substr")
    ​
    state = java_wnd.set_checked_state("JAVA控件")







get_selected(element, index=1, parent_element=None, timeout=10) 
---------------------------------------------------------------------------------

**方法描述** 

获取选中状态

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回是否选中 *\<bool\>* 

**调用样例** - rpa.ui.java.JavaWindow.get_selected-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    java_wnd = rpa.ui.java.catch("Pycharm",mode="substr")
    ​
    state = java_wnd.set_checked_state("JAVA控件")







text(element, index=1, parent_element=None, timeout=10) 
-------------------------------------------------------------------------

**方法描述** 

获取控件中的文本

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回文本 *\<str\>* 

**调用样例** - rpa.ui.java.JavaWindow.text-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    java_wnd = rpa.ui.java.catch("Pycharm",mode="substr")
    ​
    text= java_wnd.text("JAVA控件")







value(element, index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------

**方法描述** 

获取控件中的值

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回控件中的值 *\<str\>* 

**调用样例** - rpa.ui.java.JavaWindow.value-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    java_wnd = rpa.ui.java.catch("Pycharm",mode="substr")
    ​
    value= java_wnd.value("JAVA控件")







pos(element, index=1, parent_element=None, timeout=10) 
------------------------------------------------------------------------

**方法描述** 

获取控件坐标

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回坐标{x1,y1,x2,y2} *\<dict\>* 

**调用样例** - rpa.ui.java.JavaWindow.pos-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    java_wnd = rpa.ui.java.catch("Pycharm",mode="substr")
    ​
    pos_dict= java_wnd.pos("JAVA控件")







table(element, index=1, parent_element=None, timeout=10) 
--------------------------------------------------------------------------

**方法描述** 

获取控件表格内容

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回表格内容 *\<list\>* 

**调用样例** - rpa.ui.java.JavaWindow.table-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    java_wnd = rpa.ui.java.catch("Pycharm",mode="substr")
    ​
    table_data= java_wnd.table("JAVA控件")







screenshot(element, file, index=1, parent_element=None, timeout=10) 
-------------------------------------------------------------------------------------

**方法描述** 

控件截图

**参数说明** 

**element** *\<str\>* 控件名

**file** *\<str\>* 保存截图完成路径(含文件名)

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.java.JavaWindow.screenshot-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    java_wnd = rpa.ui.java.catch("Pycharm",mode="substr")
    path = r"D:\2_测试文件归档\java控件截图.jpg"
    ​
    java_wnd.screenshot("JAVA控件", path)







mouse_move(element, index=1, parent_element=None, timeout=10) 
-------------------------------------------------------------------------------

**方法描述** 

鼠标移入控件

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**parent_element** *\<Element\>* 父控件对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.java.JavaWindow.mouse_move-

    # 注意事项：
    # 使用此方法前请先通过捕捉控件功能捕捉对应控件元素
    # 代码调用样例如下：
    java_wnd = rpa.ui.java.catch("Pycharm",mode="substr")
    ​
    java_wnd.mouse_move("JAVA控件")







image 
=======================

click(element, button='left', index=1, offset_x=0, offset_y=0, window=None, timeout=10) 
---------------------------------------------------------------------------------------------------------

**方法描述** 

点击控件

**参数说明** 

**element** *\<str\>* 控件名

**button** *\<str\>* 鼠标键位

可选项：

* left : 左键

  

* right : 右键

  




**index** *\<int\>* 如果有多个，给出控件下标

**offset_x** *\<int\>* 横向偏移量

**offset_y** *\<int\>* 纵向偏移量

**window** *\<object\>* 控件所在窗口对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.image.click-

    # 注意事项：
    # 使用此方法需要先通过捕捉控件功能中的图像录制功能捕捉对应图像控件
    # 代码调用样例如下：
    rpa.ui.image.click("图像控件")







double_click(element, index=1, offset_x=0, offset_y=0, window=None, timeout=10) 
-------------------------------------------------------------------------------------------------

**方法描述** 

双击控件

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**offset_x** *\<int\>* 横向偏移量

**offset_y** *\<int\>* 纵向偏移量

**window** *\<object\>* 控件所在窗口对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.image.double_click-

    # 注意事项：
    # 使用此方法需要先通过捕捉控件功能中的图像录制功能捕捉对应图像控件
    # 代码调用样例如下：
    rpa.ui.image.double_click("图像控件")







input_text(element, value, simulate=False, index=1, window=None, wait_mili_seconds=20, timeout=10) 
--------------------------------------------------------------------------------------------------------------------

**方法描述** 

为控件输入文本

**参数说明** 

**element** *\<str\>* 控件名

**value** *\<str\>* 输入的内容

**simulate** *\<bool\>* 是否模拟输入

**index** *\<int\>* 如果有多个，给出控件下标

**window** *\<object\>* 控件所在窗口对象

**wait_mili_seconds** *\<int\>* 字符间输入间隔（毫秒），仅在模拟输入下有效，默认值为20，最大值100，该值设置过大可能会引起超时

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.image.input_text-

    # 注意事项：
    # 使用此方法需要先通过捕捉控件功能中的图像录制功能捕捉对应图像控件
    # 此方法执行输入时会以图像控件的锚点为起点，执行点击后进行模拟输入
    # 代码调用样例如下：
    rpa.ui.image.input_text("图像控件","RPA测试")







pos(element, index=1, window=None, timeout=10) 
----------------------------------------------------------------

**方法描述** 

获取控件坐标

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**window** *\<object\>* 控件所在窗口对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回坐标{x1,y1,x2,y2} *\<dict\>* 

**调用样例** - rpa.ui.image.pos-

    # 注意事项：
    # 使用此方法需要先通过捕捉控件功能中的图像录制功能捕捉对应图像控件
    # 代码调用样例如下：
    pos_dict = rpa.ui.image.pos("图像控件")







mouse_move(element, index=1, offset_x=0, offset_y=0, window=None, timeout=10) 
-----------------------------------------------------------------------------------------------

**方法描述** 

鼠标移入控件

**参数说明** 

**element** *\<str\>* 控件名

**index** *\<int\>* 如果有多个，给出控件下标

**offset_x** *\<int\>* 横向偏移量

**offset_y** *\<int\>* 纵向偏移量

**window** *\<object\>* 控件所在窗口对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**调用样例** - rpa.ui.image.mouse_move-

    # 注意事项：
    # 使用此方法需要先通过捕捉控件功能中的图像录制功能捕捉对应图像控件
    # 代码调用样例如下：
    rpa.ui.image.mouse_move("图像控件")







wait_loaded(element, index=1, window=None, timeout=10) 
------------------------------------------------------------------------

**方法描述** 

等待图像控件加载，成功返回True，失败返回False

**参数说明** 

**element** *\<str\>* 图像控件名

**index** *\<int\>* 如果有多个，给出控件下标

**window** *\<object\>* 控件所在窗口对象

**timeout** *\<int\>* 等待控件超时时间 单位秒

**返回值说明** 

返回是否加载成功 *\<bool\>* 

**调用样例** - rpa.ui.image.wait_loaded-

    # 注意事项：
    # 使用此方法需要先通过捕捉控件功能中的图像录制功能捕捉对应图像控件
    # 代码调用样例如下：
    flag = rpa.ui.image.wait_loaded("图像控件")







count(element) 
--------------------------------

**方法描述** 

获取控件个数

**参数说明** 

**element** *\<str\>* 控件名

**返回值说明** 

返回控件个数 *\<int\>* 

**调用样例** - rpa.ui.image.count-

    # 注意事项：
    # 使用此方法需要先通过捕捉控件功能中的图像录制功能捕捉对应图像控件
    # 代码调用样例如下：
    count = rpa.ui.image.count("图像控件")







ctrl 
======================

add(name, value, mode='json') 
-----------------------------------------------

**方法描述** 

添加控件

**参数说明** 

**name** *\<str\>* 控件名称

**value** *\<dict\>* 控件元对象

**mode** *\<str\>* 数据格式

可选项：

* json : json格式

  

* xml : xml格式

  




**调用样例** - rpa.ui.ctrl.add-

    # 注意事项：
    # 通过捕捉控件捕捉的控件信息记录在工程文件的.ctrl.json文件中
    # 此方法并不会向json新增控件信息，仅仅只是在代码执行过程中临时新增控件
    # 代码调用样例如下：
    raw = r'<wnd x:tag="tab" title="百度一下，你就知道" /><chrome x:tag="input" id="kw" />'
    rpa.ui.ctrl.add("新增控件测试",raw,mode="xml")







get(name, mode='json') 
----------------------------------------

**方法描述** 

获取控件元对象

**参数说明** 

**name** *\<str\>* 控件名称

**mode** *\<str\>* 返回数据格式

可选项：

* json : 返回json格式

  

* xml : 返回xml格式

  




**返回值说明** 

返回控件元对象 *\<list\>* 

**调用样例** - rpa.ui.ctrl.get-

    # 注意事项：
    # 使用此方法需要先通过捕捉控件功能捕捉对应控件
    # 将mode参数指定为xml时，将返回字符串，字符串内容形式可参阅编辑控件窗口
    # 代码调用样例如下：
    beta = rpa.ui.ctrl.get("百度一下",mode="xml")







remove(name) 
------------------------------

**方法描述** 

删除控件

**参数说明** 

**name** *\<str\>* 控件名称

**调用样例** - rpa.ui.ctrl.remove-

    # 注意事项：
    # 通过捕捉控件捕捉的控件信息记录在工程文件的.ctrl.json文件中
    # 此方法并不会删除json文件中的控件信息，仅仅只是在代码执行过程中将指定的控件禁用
    # 代码调用样例如下：
    rpa.ui.ctrl.remove("百度一下")







update(name, value, mode='json') 
--------------------------------------------------

**方法描述** 

更新控件

**参数说明** 

**name** *\<str\>* 控件名称

**value** *\<dict\>* 控件元对象

**mode** *\<str\>* 数据格式

可选项：

* json : json格式

  

* xml : xml格式

  




**调用样例** - rpa.ui.ctrl.update-

    # 注意事项：
    # 通过捕捉控件捕捉的控件信息记录在工程文件的.ctrl.json文件中
    # 此方法并不会修改json文件中的控件信息，仅仅只是在代码执行过程中更新控件信息
    # 代码调用样例如下，本例中先在chrome浏览器上捕捉了控件，然后通过此方法将控件浏览器信息改为ie：
    page1 = rpa.app.chrome.create('www.baidu.com')
    page1.input_text('百度一下', 'Alibaba-chrome')
    ​
    raw_ie = r'<wnd x:tag="tab" title="百度一下，你就知道" /><ie x:tag="input" id="kw" />'
    rpa.ui.ctrl.update("百度一下",raw_ie,mode="xml")
    page2 = rpa.app.ie.create('www.baidu.com')
    page2.input_text('百度一下', 'Alibaba')









