project 
============================

本文档主要介绍编辑器组件面板中Project目录下相关组件的使用。

params 
========================

Params参数面板 
----------------------------

#取值params\["参数1"\]#设置值params\["参数1"\] = value方法

**调用样例** - rpa.project.params.Params-

    # 注意事项：
    # 1. 使用此对象前，需要先在参数面板中设置参数
    # 2. 使用此对象设置的参数值，最终都会以字符串的形式返回
    # 代码调用样例如下，运行后会将参数面板中名为"参数1"的参数值设为'123',使用变量arg1接受此值
    rpa.project.params["参数1"] = 123
    arg1 = rpa.project.params["参数1"]







datatable 
===========================

add_row(value=None) 
-------------------------------------

**方法描述** 

增加一行

**返回值说明** 

返回最后一行行号 *\<int\>* 

**调用样例** - rpa.project.datatable.add_row-

    # 注意事项：行数据个数多于标题列数时，多出的数据不会添加到数据视图中，
    # 例如：标题列有2列，新增一行数据[1,2,3]，则数据视图上只会写入1，2
    # 代码调用样例如下，运行后会在数据视图新增一行，并返回最后一行行号
    datatable = rpa.project.datatable
    new_row_num = datatable.add_row([1,2,3])







clear() 
-------------------------

**方法描述** 

清空数据视图

**调用样例** - rpa.project.datatable.clear-

    # 注意事项：无
    # 代码调用样例如下，运行后会清空数据视图中所有数据：
    datatable = rpa.project.datatable
    datatable.close()







insert_row(row) 
---------------------------------

**方法描述** 

插入一行数据

**参数说明** 

**row** *\<int\>* 行号

**调用样例** - rpa.project.datatable.insert_row-

    # 注意事项：插入行前需要确保数据视图中已有对应行。
    # 例如向第2行插入数据前，需要确保数据视图至少有2行。
    # 代码调用样例如下，运行后会在已有数据第2行之前插入一行，
    # 可通过datatable[2] 来设置新插入的行的数据:
    datatable = rpa.project.datatable
    datatable.insert_row(2)
    datatable[2] = ['通过Insert方法插入','将在指定行号前执行插入']









set_checked(row, value=True) 
----------------------------------------------

**方法描述** 

设置行的勾选状态

**参数说明** 

**row** *\<int\>* 行号

**value** *\<bool\>* 勾选状态

**调用样例** - rpa.project.datatable.set_checked-

    # 注意事项：使用前请确保指定的行已存在。
    # 代码调用样例如下，运行后会勾选第1行：
    datatable = rpa.project.datatable
    datatable.set_checked(1)







get_checked(row) 
----------------------------------

**方法描述** 

获取行的勾选状态

**参数说明** 

**row** *\<int\>* 行号

**返回值说明** 

返回行的勾选状态 *\<bool\>* 

**调用样例** - rpa.project.datatable.get_checked-

    # 注意事项：使用前请确保指定的行已存在
    # 代码调用样例如下，运行后会返回第1行的勾选结果：
    datatable = rpa.project.datatable
    flag = datatable.get_checked(1)







scroll_index(index) 
-------------------------------------

**方法描述** 

设置焦点所在行

**参数说明** 

**index** *\<int\>* 要设置焦点的行下标

**调用样例** - rpa.project.datatable.scroll_index-

    # 注意事项：使用前请确保指定的行已存在
    # 代码调用样例如下，运行后会将焦点定位在第三行，即选中第3行。
    datatable = rpa.project.datatable
    datatable.scroll_index(3)









resource 
==========================

read(resource_name, encoding='utf-8') 
-------------------------------------------------------

**方法描述** 

读取资源文件内容

**参数说明** 

**resource_name** *\<str\>* 资源文件名称，相对于工程中resources文件夹目录

**encoding** *\<str\>* 资源文件的编码格式，默认utf-8

**返回值说明** 

返回资源文件内容 *\<str\>* 

**调用样例** - rpa.project.resource.read-

    # 注意事项：使用前请确认在工程面板-资源，对应的文件夹下存在待读取的文本文件
    # 代码调用样例如下，运行后会返回文件的文本内容：
    content = rpa.project.resource.read('test.txt')







get_path(resource_name=None) 
----------------------------------------------

**方法描述** 

获取资源文件的路径

**参数说明** 

**resource_name** *\<str\>* 资源文件名称，相对于工程中resources文件夹目录

**返回值说明** 

返回资源文件的路径 *\<str\>* 

**调用样例** - rpa.project.resource.get_path-

    # 注意事项：使用前请确认在工程面板-资源，对应的文件夹下存在待读取的文本文件
    # 代码调用样例如下，运行后会返回文件的完整绝对路径：
    path = rpa.project.resource.get_path(r'file_test\test1.txt')







