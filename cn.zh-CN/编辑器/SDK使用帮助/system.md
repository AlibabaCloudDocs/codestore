system 
===========================

本文档主要介绍编辑器组件面板中System目录下相关组件的使用。

no_disturb_mode 
=================================

start() 
-------------------------

**方法描述** 

开启勿扰模式

**调用样例** - rpa.system.no_disturb_mode.start-

    # 注意事项：调试、执行此方法需要管理员权限
    # 代码调用样例如下，运行后会开启勿扰模式，再执行随后的脚本，本例中创建网页窗口将以勿扰模式进行
    # 运行后，在脚本全部执行完之前，屏幕上会提示勿扰，期间无法进行鼠标键盘操作。
    rpa.system.no_disturb_mode.start()
    rpa.app.chrome.create('www.baidu.com')
    sleep(5)







stop() 
------------------------

**方法描述** 

停止勿扰模式

**调用样例** - rpa.system.no_disturb_mode.stop-

    # 注意事项：调试、执行此方法需要管理员权限
    # 代码调用样例如下，运行后会关闭已开启的勿扰模式。
    rpa.system.no_disturb_mode.stop()







screen_unlocker 
=================================

start() 
-------------------------

**方法描述** 

开始自动解锁

**调用样例** - rpa.system.screen_unlocker.start-

    # 注意事项：
    # 1.调试、执行此方法需要管理员权限
    # 2.如果有锁屏密码，请先使用set_password方法设置密码
    # 代码调用样例如下，验证时请将密码'123456'改为本机实际锁屏解锁密码，运行后会在程序执行期间会自动解锁
    # 使用快捷键win+L可以快速锁屏验证效果
    rpa.system.screen_unlocker.set_password('123456')
    rpa.system.screen_unlocker.start()
    sleep(10)







stop() 
------------------------

**方法描述** 

停止自动解锁

**调用样例** - rpa.system.screen_unlocker.stop-

    # 注意事项：调试、执行此方法需要管理员权限
    # 代码调用样例如下，运行后会关闭已开启的自动解锁功能。
    rpa.system.screen_unlocker.stop()







set_password(value) 
-------------------------------------

**方法描述** 

设置密码

**参数说明** 

**value** *\<str\>* 密码

**调用样例** - rpa.system.screen_unlocker.set_password-

    # 注意事项：调试、执行此方法需要管理员权限
    # 代码调用样例如下，在开启自动解锁屏幕之前，可用此方法设置本机解锁密码
    rpa.system.screen_unlocker.set_password('123456')







dialog 
========================

msgbox(title, message, message_max_length=1000, disappear_time=-1, message_location='center') 
---------------------------------------------------------------------------------------------------------------

**方法描述** 

弹消息框

**参数说明** 

**title** *\<str\>* 标题

**message** *\<str\>* 信息

**message_max_length** *\<int\>* 信息文本最大长度

**disappear_time** *\<int\>* 消息框自动消失时间(s)，默认为-1不会自动消失

**message_location** *\<str\>* 提示框位置

可选项：

* center : 居中(默认)

  

* top : 顶部

  

* bottom : 底部

  

* bottom_right : 右下角

  




**返回值说明** 

返回选择结果(ok) *\<str\>* 

**调用样例** - rpa.system.dialog.msgbox-

    # 注意事项：无
    # 代码调用样例如下，运行后会弹出带确定按钮的提示框：
    rpa.system.dialog.msgbox('提示框','这是由RPA弹出的提示框')







choose(title, message) 
----------------------------------------

**方法描述** 

弹选择框

**参数说明** 

**title** *\<str\>* 标题

**message** *\<str\>* 信息

**返回值说明** 

返回选择结果 *\<bool\>* 

**调用样例** - rpa.system.dialog.choose-

    # 注意事项：无
    # 代码调用样例如下，运行后会弹出带是否按钮的选择框，根据选择结果返回True或者False
    rpa.system.dialog.choose('选择框','这是由RPA弹出的选择框')







choose_with_multi_style(title, message, message_level='info', choose_type='yes_no', choose_location='center') 
-------------------------------------------------------------------------------------------------------------------------------

**方法描述** 

弹选择框，可选择多种样式

**参数说明** 

**title** *\<str\>* 标题

**message** *\<str\>* 信息

**message_level** *\<str\>* 信息等级

可选项：

* info : 信息(默认)

  

* warn : 警告

  

* error : 错误

  




**choose_type** *\<str\>* 按钮样式

可选项：

* ok : 只显示确定按钮(默认）

  

* yes_no : 显示是和否按钮

  

* abort_retry_ignore : 显示放弃、重试和跳过按钮

  

* yes_no_cancel : 显示是、否和取消按钮

  

* retry_cancel : 显示重试和取消按钮

  

* ok_cancel : 显示确定和取消按钮

  




**choose_location** *\<str\>* 弹窗位置

可选项：

* center : 居中(默认)

  

* top : 顶部

  

* bottom : 底部

  

* bottom_right : 右下角

  




**返回值说明** 

返回选择结果代表的字符串 *\<str\>* 

**调用样例** - rpa.system.dialog.choose_with_multi_style-

    # 注意事项：无
    # 代码调用样例如下，运行后会根据设置弹出不同样式的选择框，根据选择结果返回对应字符串
    rpa.system.dialog.choose_with_multi_style('选择框','这是由RPA弹出的选择框',message_level='warn',choose_type='yes_no_cancel')







input(title, msg, type='text') 
------------------------------------------------

**方法描述** 

弹输入框

**参数说明** 

**title** *\<str\>* 标题

**msg** *\<str\>* 信息

可选项：

* type : 输入框类型 'text'\|'pwd'

  




**返回值说明** 

返回输入的内容 *\<str\>* 

**调用样例** - rpa.system.dialog.input-

    # 注意事项：无
    # 代码调用样例如下，运行后会弹出带确定和取消按钮的输入框，点击确定后返回输入的字符串
    rpa.system.dialog.input('输入框','这是由RPA弹出的输入框')









inputbox(title, content, watermark_text='请输入') 
----------------------------------------------------------------

**方法描述** 

弹输入框

**参数说明** 

**title** *\<str\>* 标题

**content** *\<str\>* 信息

**watermark_text** *\<str\>* 水印文字

**返回值说明** 

返回输入的内容 *\<str\>* 

**调用样例** - rpa.system.dialog.inputbox-

    # 注意事项：无
    # 代码调用样例如下，运行后会弹出带水印文字及确定按钮的输入框，点击确定后返回输入的字符串
    rpa.system.dialog.inputbox('输入框','这是由RPA弹出的输入框')









option(title, msg, default, data) 
---------------------------------------------------

**方法描述** 

弹下拉框

**参数说明** 

**title** *\<str\>* 标题

**msg** *\<str\>* 信息

**default** *\<str\>* 默认值

**data** *\<list\>* 备选值

**返回值说明** 

返回选择结果 *\<str\>* 

**调用样例** - rpa.system.dialog.option-

    # 注意事项：无
    # 代码调用样例如下，运行后会弹出带确定及取消按钮的下拉框，点击确认后返回所选择的字符串
    option_list = ['阿里云','RPA','引领企业智能']
    rpa.system.dialog.option('下拉框','这是由RPA弹出的下拉框','默认值',option_list)






