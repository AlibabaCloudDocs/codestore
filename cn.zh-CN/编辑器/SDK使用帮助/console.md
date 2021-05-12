console 
============================

本文档主要介绍编辑器组件面板中Console目录下相关组件的使用。

asset 
=======================

get_value(name) 
---------------------------------

**方法描述** 

获取资产变量的值,需要有变量使用权限

**参数说明** 

**name** *\<str\>* 资产变量名

**调用样例** - rpa.console.asset.get_value-

    # 注意事项：
    # 1. 使用前请确认控制台-资产管理页面有对应的资产变量，且当前账号有资产变量的使用权限
    # 2. 此方法无法获取类型为"账号密码"的资产变量
    # 代码调用样例如下，运行后会获取对应资产变量的文本值：
    account = rpa.console.asset.get_value('test_account')









fill_account_to_page(name, user_element, password_element, page, wait_mili_seconds=20) 
--------------------------------------------------------------------------------------------------------

**方法描述** 

设置账号密码类型的资产变量值到页面

**参数说明** 

**name** *\<str\>* 资产变量名

**user_element** *\<str\>* 用户名控件

**password_element** *\<str\>* 密码控件

**page** *\<str\>* 浏览器页面对象

**调用样例** - rpa.console.asset.fill_account_to_page-

    # 注意事项：
    # 1. 使用前请确认控制台-资产管理页面有对应的资产变量，且当前账号有资产变量的使用权限
    # 2. 此方法只能使用类型为"账号密码"的资产变量
    # 3. 使用前请确认账号框和密码框控件是可输入状态。
    # 代码调用样例如下，运行后会读取资产变量并向账号、密码框输入对应内容：
    page = rpa.app.chrome.create(r'login.taobao.com/member/login.jhtml')
    rpa.console.asset.fill_account_to_page('my_taobao','账号框','密码框',page)







logger 
========================

info(values) 
------------------------------

**方法描述** 

记录信息日志

**调用样例** - rpa.console.logger.info-

    # 注意事项：此方法使用不定长参数，可添加任意多个内容，最终以字符串形式输出到日志面板
    # 代码调用样例如下：
    rpa.console.logger.info('RPA-Logger' , '类型为info')







warn(values) 
------------------------------

**方法描述** 

记录警告日志

**调用样例** - rpa.console.logger.warn-

    # 注意事项：此方法使用不定长参数，可添加任意多个内容，最终以字符串形式输出到日志面板
    # 代码调用样例如下：
    rpa.console.logger.warn('RPA-Logger' , '类型为warn')







error(values) 
-------------------------------

**方法描述** 

记录错误日志

**调用样例** - rpa.console.logger.error-

    # 注意事项：此方法使用不定长参数，可添加任意多个内容，最终以字符串形式输出到日志面板
    # 代码调用样例如下：
    rpa.console.logger.error('RPA-Logger' , '类型为error')









workbench 
===========================

task_result(content) 
--------------------------------------

**方法描述** 

设置服务型机器人任务结果

**参数说明** 

**content** *\<str\>* 任务结果

**调用样例** - rpa.console.workbench.task_result-

    # 注意事项：此方法无法进行本地调试，需要发布成应用，通过API调用，
    # 调用成功后使用queryServiceResult服务获取对应结果。
    # 代码调用样例如下，发布成应用后，通过API调用此机器人应用
    # 会在最终的返回值的data中，得到自定义的任务结果
    json_result = '{"employees": [{"firstName": "Bill","lastName": "Gates"}]}'
    rpa.console.workbench.task_result(json_result)







record(status=None) 
-------------------------------------

**方法描述** 

上传数据记录

**调用样例** - rpa.console.workbench.record-

    # 注意事项：
    # 代码调用样例如下：
    rpa.console.workbench.record('success')







