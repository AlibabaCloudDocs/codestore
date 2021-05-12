EXCEL组件 
============================

本文档主要介绍阿里云RPA可视化编辑模式下，EXCEL类组件的操作示例。



启动Excel 
----------------------------

**必要前置组件：** 无

1. 在画布中新增"启动Excel"组件，启动方式选择新建Excel，在新建Excel文件路径参数栏点击文件夹按钮，进入文件路径界面，选择好指定的文件夹后，在文件名栏输入带excel文件后缀（.xlsx）的文件名，随后点击保存即可，点击运行。

![启动Excel](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8356759161/p263344.png)

2. 运行后，程序会在指定路径下新建一个指定名称的EXCEL文件，并打开，切换窗口可以查看对应空白EXCEL文件。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![启动Excel_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9356759161/p263345.png)

![启动Excel_3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9356759161/p263349.png)



获取已打开的Excel 
--------------------------------

**必要前置组件：** 无

1. 首先手动打开多个EXCEL文件，其中有一个EXCEL文件名为"市场部.xlsx"，在画布中新增"获取已打开的Excel"组件，在查找内容中输入需要获取的带拓展名的文件名，本例中为"市场部.xlsx"，点击运行。

![获取已打开的EXCEL_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9356759161/p263355.png)

2. 运行后，程序会自动在当前打开的EXCEL文件中，找到市场部.xlsx这个特定的文件，将其记录为Excel对象v_excel_obj_1（如果已打开的EXCEL文件汇总无市场部.xlsx）供后续操作。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。



获取当前激活的Sheet页 
----------------------------------

**必要前置组件：** [启动Excel](#section-it3-sv5-kem) **\|** [获取已打开的Excel](#section-y08-4yu-583)

1. 使用"启动Excel"组件启动一个EXCEL文件，随后新增"获取当前激活的Sheet页"组件，在组件参数中填选已经打开的excel对象，点击运行。

![获取当前激活的Sheet页_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9356759161/p263356.png)

2. 运行后，程序会打开指定EXCEL文件，并获取默认激活的sheet页供后续操作。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息



保存Excel 
----------------------------

**必要前置组件：** [启动Excel](#section-it3-sv5-kem) **\|** [获取已打开的Excel](#section-y08-4yu-583)

1. 使用"启动Excel"组件启动一个EXCEL文件，此例中为运营部.xlsx，随后新增"保存Excel"组件，在组件参数中填选已经打开的excel对象，保存方式选为另存为，在另存为路径中填选新文件路径：运营部-副本.xlsx，点击运行。

![保存Excel_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9356759161/p263358.png)

2. 运行后，程序会打开指定EXCEL文件，并将文件另存为副本。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![保存Excel_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9356759161/p263359.png)





关闭Excel 
----------------------------

**必要前置组件：** [启动Excel](#section-it3-sv5-kem) **\|** [获取已打开的Excel](#section-y08-4yu-583)

1. 使用"启动Excel组件"启动一个EXCEL文件，此例中为运营部.xlsx，随后新增"关闭Excel"组件，在组件参数中填选已经打开的excel对象，点击运行。

![关闭Excel_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9356759161/p263360.png)

2. 运行后，程序会打开指定EXCEL文件，然后关闭EXCEL并保存（保存在原路径）。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。





创建Sheet页 
-----------------------------

**必要前置组件：** [启动Excel](#section-it3-sv5-kem) **\|** [获取已打开的Excel](#section-y08-4yu-583)

1. 使用启动Excel组件启动一个EXCEL文件，随后新增"创建Sheet页"组件，在属性区填选已打开的Excel对象，并输入要新建的Sheet页名称，完成后点击运行。

![创建Sheet页_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9356759161/p263361.png)

2. 运行后，程序会打开指定EXCEL文件，在左下角sheet页签首个位置，新建一个名为"RPA测试"的sheet页。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![创建Sheet页_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/0456759161/p263363.png)



删除Sheet页 
-----------------------------

**必要前置组件：** [启动Excel](#section-it3-sv5-kem) **\|** [获取已打开的Excel](#section-y08-4yu-583)

1. 使用启动Excel组件启动一个EXCEL文件，此EXCEL文件中有两个sheet页（只有一个sheet页无法进行删除sheet页操作），随后新增"删除Sheet页"组件，在属性区填选已打开的Excel对象，并输入要删除的Sheet页名称，完成后点击运行。

![删除Sheet页_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/0456759161/p263365.png)![删除Sheet_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/0456759161/p263366.png)

2. 运行后，程序会打开指定EXCEL文件，删除其中名为"RPA测试"的sheet页。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![删除Sheet_3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/0456759161/p263367.png)



激活Sheet页 
-----------------------------

**必要前置组件：** [启动Excel](#section-it3-sv5-kem) **\|** [获取已打开的Excel](#section-y08-4yu-583)

1. 使用启动Excel组件启动一个EXCEL文件，此EXCEL文件中有两个sheet页，随后新增"激活Sheet页"组件，在属性区填选已打开的Excel对象，并输入要激活的Sheet页名称，完成后点击运行。

![激活Sheet页_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/0456759161/p263368.png)

2. 运行之后，程序会打开指定EXCEL文件，不管其默认打开的的是何sheet页，都会激活其中名为"RPA测试"的sheet页。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![激活Sheet页_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/0456759161/p263369.png)



重命名Sheet页 
------------------------------

**必要前置组件：** [启动Excel](#section-it3-sv5-kem) **\|** [获取已打开的Excel](#section-y08-4yu-583)

1. 使用启动Excel组件启动一个EXCEL文件，此EXCEL文件中有两个sheet页，其中一个名为"RPA测试"，随后新增"重命名Sheet页"组件，在属性区填选已打开的Excel对象，并输入要改名的Sheet页名称，随后输入sheet页的新名称，完成后点击运行。

![重命名Sheet页_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/0456759161/p263370.png)

2. 运行之后，程序会打开指定EXCEL文件，将其中名为"RPA测试"的sheet页更名为"RPA测试-改名之后"。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![重命名Sheet页_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/0456759161/p263371.png)



获取Excel单元格的值 
---------------------------------

**必要前置组件：** [获取当前激活的Sheet页](#section-qy3-3t0-rev) **\|** [创建Sheet页](#section-hos-4l4-bdc) **\|** [激活Sheet页](/cn.zh-CN/编辑器/可视化组件基本使用样例/EXCEL组件.md)

1. 使用启动Excel组件启动一个EXCEL文件，并使用获取当前激活的Sheet页组件获取要操作的sheet页，随后新增"获取Excel单元格的值"组件，在属性区填选已打开的Sheet对象，并输入要读取的单元格行号和列号，此例中使用默认值，为了直观查看获取到的单元格的值，在此组件后新增弹出提示框组件，提示内容选择单元格的值v_cell_value_1，完成后点击运行。

![获取Excel单元格的值_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/0456759161/p263379.png)

2. 运行之后，程序会在指定的sheet页上，读取单元格"A1"的值，并将此值保存在v_cell_value_1。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![获取单元格值_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1456759161/p263380.png)

获取Excel区域的值 
--------------------------------

**必要前置组件：** [获取当前激活的Sheet页](#section-qy3-3t0-rev) **\|** [创建Sheet页](#section-hos-4l4-bdc) **\|** [激活Sheet页](/cn.zh-CN/编辑器/可视化组件基本使用样例/EXCEL组件.md)

1. 使用启动Excel组件启动一个EXCEL文件，并使用获取当前激活的Sheet页组件获取要操作的sheet页，随后新增"获取Excel区域的值"组件，在属性区填选已打开的Sheet对象，并输入要读取区域的起止单元格行号和列号，此例中使用默认值，为了直观查看获取到的单元格的值，在此组件后新增记录日志组件，提示内容选择区域的值v_cell_range_values_1，完成后点击运行。

![获取Excel区域值_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1456759161/p263381.png)

2. 运行之后，程序会在指定的sheet页上，读取区域"A1:B2"的值，并将此值保存在v_cell_range_values_1。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![获取Excel区域值_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1456759161/p263383.png)



获取Excel行的值 
-------------------------------

**必要前置组件：** [获取当前激活的Sheet页](#section-qy3-3t0-rev) **\|** [创建Sheet页](#section-hos-4l4-bdc) **\|** [激活Sheet页](/cn.zh-CN/编辑器/可视化组件基本使用样例/EXCEL组件.md)

1. 使用启动Excel组件启动一个EXCEL文件，并使用获取当前激活的Sheet页组件获取要操作的sheet页，随后新增"获取Excel行的值"组件，在属性区填选已打开的Sheet对象，并输入要读取行号，此例中使用默认值，为了直观查看获取到的行的值，在此组件后新增记录日志组件，提示内容选择行值v_cell_row_values_1，完成后点击运行。

![获取Excel行的值_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1456759161/p263385.png)

2. 运行之后，程序会在指定的sheet页上，读取第1行的值，并将此值保存在v_cell_row_values_1。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![获取Excel行的值_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1456759161/p263386.png)



获取Excel列的值 
-------------------------------

**必要前置组件：** [获取当前激活的Sheet页](#section-qy3-3t0-rev) **\|** [创建Sheet页](#section-hos-4l4-bdc) **\|** [激活Sheet页](/cn.zh-CN/编辑器/可视化组件基本使用样例/EXCEL组件.md)

1. 使用启动Excel组件启动一个EXCEL文件，并使用获取当前激活的Sheet页组件获取要操作的sheet页，随后新增"获取Excel列的值"组件，在属性区填选已打开的Sheet对象，并输入要读取列号，此例中使用默认值，为了直观查看获取到的列的值，在此组件后新增记录日志组件，提示内容选择列值v_cell_column_values_1，完成后点击运行。

![获取Excel列的值_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1456759161/p263387.png)

2. 运行之后，程序会在指定的sheet页上，读取第1列的值，并将此值保存在v_cell_column_values_1。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![获取Excel列的值_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1456759161/p263388.png)



写入Excel单元格 
-------------------------------

**必要前置组件：** [获取当前激活的Sheet页](#section-qy3-3t0-rev) **\|** [创建Sheet页](#section-hos-4l4-bdc) **\|** [激活Sheet页](/cn.zh-CN/编辑器/可视化组件基本使用样例/EXCEL组件.md)

1. 使用启动Excel组件启动一个EXCEL文件，并使用获取当前激活的Sheet页组件获取要操作的sheet页，随后新增"写入Excel单元格"组件，在属性区填选已打开的Sheet对象，并输入要写入的单元格行号和列号，此例中使用默认值，在写入内容中填入：RPA测试，完成后点击运行。

![写入Excel单元格_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1456759161/p263389.png)

2. 运行之后，程序会在指定的sheet页上，向A1单元格写入"RPA测试"。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![写入单元格_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1456759161/p263391.png)



写入Excel区域 
------------------------------

**必要前置组件：** [获取当前激活的Sheet页](#section-qy3-3t0-rev) **\|** [创建Sheet页](#section-hos-4l4-bdc) **\|** [激活Sheet页](/cn.zh-CN/编辑器/可视化组件基本使用样例/EXCEL组件.md)

1. 使用启动Excel组件启动一个EXCEL文件，并使用获取当前激活的Sheet页组件获取要操作的sheet页，随后新增"写入Excel区域"组件，在属性区填选已打开的Sheet对象，并输入待写入区域的起始单元格行号和列号，此例中使用默认值，在写入内容中，选择编辑表达式，在表达式窗口中填入：\[\["A1","B1"\],\["A2","B2"\]\]，完成后点击运行。

![写入Excel区域_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1456759161/p263392.png)![写入Excel区域_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/1456759161/p263393.png)

2. 运行之后，程序会在指定的sheet页上，从A1单元格开始，写入一个2X2的数据区域，如下图所示。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![写入Excel区域_3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2456759161/p263395.png)



写入Excel行 
-----------------------------

**必要前置组件：** [获取当前激活的Sheet页](#section-qy3-3t0-rev) **\|** [创建Sheet页](#section-hos-4l4-bdc) **\|** [激活Sheet页](/cn.zh-CN/编辑器/可视化组件基本使用样例/EXCEL组件.md)

1. 使用启动Excel组件启动一个EXCEL文件，并使用获取当前激活的Sheet页组件获取要操作的sheet页，随后新增"写入Excel行"组件，在属性区填选已打开的Sheet对象，并输入待写入行的起始单元格行号和列号，此例中行使用默认值，列填入B，在写入内容中，选择编辑表达式，在表达式窗口中填入：\["A1","B1","C1"\]，完成后点击运行。

![写入Excel行_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2456759161/p263398.png)![写入Excel行_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2456759161/p263400.png)

2. 运行之后，程序会在指定的sheet页上，从B1单元格开始，在第一行写入一行数据，如下图所示。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![写入Excel行_3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2456759161/p263401.png)



在Excel末尾写入一行 
---------------------------------

**必要前置组件：** [获取当前激活的Sheet页](#section-qy3-3t0-rev) **\|** [创建Sheet页](#section-hos-4l4-bdc) **\|** [激活Sheet页](/cn.zh-CN/编辑器/可视化组件基本使用样例/EXCEL组件.md)

1. 使用启动Excel组件启动一个EXCEL文件，并使用获取当前激活的Sheet页组件获取要操作的sheet页，随后新增"在Excel末尾写入一行"组件，在属性区填选已打开的Sheet对象，并输入待写入行的起始单元格行号和列号，此例中行使用默认值，列填入B，在写入内容中，选择编辑表达式，在表达式窗口中填入：\["A1","B1","C1"\]，完成后点击运行。

![在Excel末尾写入一行_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2456759161/p263403.png)![在Excel末尾写入一行_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2456759161/p263404.png)

2. 运行之后，程序会在指定的sheet页上，新增一行写入数据，如下图所示，原本EXCEL文件上有一行数据，新输入将自动新增一行写入。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![在Excel末尾写入一行_3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2456759161/p263409.png)



写入Excel列 
-----------------------------

**必要前置组件：** [获取当前激活的Sheet页](#section-qy3-3t0-rev) **\|** [创建Sheet页](#section-hos-4l4-bdc) **\|** [激活Sheet页](/cn.zh-CN/编辑器/可视化组件基本使用样例/EXCEL组件.md)

1. 使用"启动Excel"组件启动一个EXCEL文件，并使用获取当前激活的Sheet页组件获取要操作的sheet页，随后新增"写入Excel列"组件，在属性区填选已打开的Sheet对象，并输入待写入行的起始单元格行号和列号，此例中行写入行号2，列使用默认值，在写入内容中，选择编辑表达式，在表达式窗口中填入：\["A1","B1","C1"\]，完成后点击运行。

![写入Excel列_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2456759161/p263414.png)![写入Excel列_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2456759161/p263415.png)

2. 运行之后，程序会在指定的sheet页上，从A2单元格开始，在A列写入一列数据，如下图所示。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![写入Excel列_3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2456759161/p263416.png)



设置Excel区域格式 
--------------------------------

**必要前置组件：** [获取当前激活的Sheet页](#section-qy3-3t0-rev) **\|** [创建Sheet页](#section-hos-4l4-bdc) **\|** [激活Sheet页](/cn.zh-CN/编辑器/可视化组件基本使用样例/EXCEL组件.md)

1. 准备一张EXCEL表，A1:B2区域写入一般数字格式，随后使用"启动Excel"组件启动此EXCEL文件，并使用"获取当前激活的Sheet页"组件获取要操作的sheet页，随后新增"设置Excel区域格式"组件，在属性区填选已打开的Sheet对象，并输入要设置格式区域的起止单元格行号和列号，此例中使用默认值，区域的数字格式选为0.00，即保留两位小数，完成后点击运行。

![设置Excel区域格式_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2456759161/p263423.png)![设置Excel区域格式_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3456759161/p263424.png)

2. 运行之后，程序会在指定的sheet页上，将A1:B2区域的值格式设置为0.00形式，效果如下图所示。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![设置Excel区域格式_3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3456759161/p263427.png)



查找Excel单元格 
-------------------------------

**必要前置组件：** [获取当前激活的Sheet页](#section-qy3-3t0-rev) **\|** [创建Sheet页](#section-hos-4l4-bdc) **\|** [激活Sheet页](/cn.zh-CN/编辑器/可视化组件基本使用样例/EXCEL组件.md)

1. 使用"启动Excel"组件启动一个EXCEL文件，并使用"获取当前激活的Sheet页"组件获取要操作的sheet页，随后新增"获取Excel区域的值"组件，在属性区填选已打开的Sheet对象，并输入要读取区域的起止单元格行号和列号，此例中使用默认值，为了直观查看获取到的单元格的值，在此组件后新增记录日志组件，提示内容选择区域的值v_cell_range_values_1，完成后点击运行。

![查找Excel单元格_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3456759161/p263497.png)![查找Excel单元格_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3456759161/p263498.png)

2. 程序运行后，会打开对应的EXCEL文件，并在激活的sheet页中找出所有值内容包含"查找的值"的单元格位置，输出成形如\['B2','C3','A1'\]的列表。

![查找Excel单元格_3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3456759161/p263500.png)



复制Excel单元格 
-------------------------------

**必要前置组件：** [启动Excel](#section-it3-sv5-kem) **\|** [获取已打开的Excel](#section-y08-4yu-583)

1. 使用"启动Excel"组件启动一个EXCEL文件，随后新增"复制Excel单元格"组件，在组件中填选Excel对象，sheet页名称，以及要复制的单元格行列。

![复制Excel单元格_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3456759161/p263503.png)

2. 流程运行后，程序将打开指定Excel文件，并在指定的Sheet页"Sheet1"上，复制A1单元格的内容，要验证复制的结果，仅需在单元格空白区域直接粘贴即可。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![复制Excel单元格_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3456759161/p263504.png)



粘贴Excel单元格 
-------------------------------

**必要前置组件：(** [启动Excel](#section-it3-sv5-kem) **\|** [获取已打开的Excel](#section-y08-4yu-583) **) \&** [复制Excel单元格](#section-5xx-aps-g5m)

1. 使用"启动Excel"组件启动一个EXCEL文件，随后新增"复制Excel单元格"组件，在组件中填选Excel对象，sheet页名称，以及要复制的单元格行列。然后在复制Excel单元格组件后新增粘贴Excel单元格组件，填选相关参数，将复制的内容粘贴到F1单元格中。

![粘贴Excel单元格_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3456759161/p263523.png)

2. 流程运行后，程序将打开指定Excel文件，并在指定的Sheet页"Sheet1"上，复制A1单元格的内容，随后将复制的内容及格式完全粘贴到F1单元格上。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![粘贴Excel单元格_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3456759161/p263524.png)



复制Excel区域 
------------------------------

**必要前置组件：** [启动Excel](#section-it3-sv5-kem) **\|** [获取已打开的Excel](#section-y08-4yu-583)

1. 使用"启动Excel"组件启动一个EXCEL文件，随后新增"复制Excel区域"组件，在组件中填选Excel对象，sheet页名称，以及要复制的区域。

![复制Excel区域_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3456759161/p263549.png)

2. 流程运行后，程序将打开指定Excel文件，并在指定的Sheet页"Sheet1"上，复制A1:B2区域的内容，要验证复制的结果，仅需在单元格空白区域直接粘贴即可。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![复制Excel区域_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/3456759161/p263550.png)



粘贴Excel区域 
------------------------------

**必要前置组件：** **(** [启动Excel](#section-it3-sv5-kem) **\|** [获取已打开的Excel](#section-y08-4yu-583) **) \&** [复制Excel区域](#section-ovr-3jy-5s5)

1. 使用"启动Excel"组件启动一个EXCEL文件，随后新增"复制Excel区域"组件，在组件中填选Excel对象，sheet页名称，以及要复制的单元格区域。然后在复制Excel单元格组件后新增粘贴Excel区域组件，填选相关参数，将复制的内容从F1单元格开始粘贴到对应区域。

![粘贴Excel区域_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4456759161/p263554.png)

2. 流程运行后，程序将打开指定Excel文件，并在指定的Sheet页"Sheet1"上，复制A1:B2区域的内容，随后将复制的内容及格式完全粘贴到F1:G2区域中。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![粘贴Excel区域_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4456759161/p263555.png)



复制Excel行 
-----------------------------

**必要前置组件：** [启动Excel](#section-it3-sv5-kem) **\|** [获取已打开的Excel](#section-y08-4yu-583)

1. 使用"启动Excel"组件启动一个EXCEL文件，随后新增"复制Excel行"组件，在组件中填选Excel对象，sheet页名称，以及要复制的行号。

![复制Excel行_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4456759161/p263556.png)

2. 流程运行后，程序将打开指定Excel文件，并在指定的Sheet页"Sheet1"上，复制第一行的内容，要验证复制的结果，仅需在空白行直接粘贴即可。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![复制Excel行_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4456759161/p263557.png)



粘贴Excel行 
-----------------------------

**必要前置组件：** **(** [启动Excel](#section-it3-sv5-kem) **\|** [获取已打开的Excel](#section-y08-4yu-583) **) \&** [复制Excel行](#section-ivj-h0m-tu5)

1. 使用"启动Excel"组件启动一个EXCEL文件，随后新增"复制Excel行"组件，在组件中填选Excel对象，sheet页名称，以及要复制的行。然后在复制Excel单元格组件后新增粘贴Excel行组件，填选相关参数，将复制的内容粘贴到第6行。

![粘贴Excel行_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4456759161/p263560.png)

2. 流程运行后，程序将打开指定Excel文件，并在指定的Sheet页"Sheet1"上，复制第1行的内容，随后将复制的内容及格式完全粘贴到第6行。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![粘贴Excel行_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4456759161/p263561.png)



复制Excel列 
-----------------------------

**必要前置组件：** [启动Excel](#section-it3-sv5-kem) **\|** [获取已打开的Excel](#section-y08-4yu-583)

1. 使用"启动Excel"组件启动一个EXCEL文件，随后新增"复制Excel列"组件，在组件中填选Excel对象，sheet页名称，以及要复制的列号。

![复制Excel列_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4456759161/p263565.png)

2. 流程运行后，程序将打开指定Excel文件，并在指定的Sheet页"Sheet1"上，复制第一列的内容，要验证复制的结果，仅需在空白列直接粘贴即可。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![复制Excel列_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4456759161/p263567.png)



粘贴Excel列 
-----------------------------

**必要前置组件：** **(** [启动Excel](#section-it3-sv5-kem) **\|** [获取已打开的Excel](#section-y08-4yu-583) **) \&** [复制Excel列](#section-y9l-ucf-gn6)

1. 使用"启动Excel"组件启动一个EXCEL文件，随后新增"复制Excel列"组件，在组件中填选Excel对象，sheet页名称，以及要复制的行。然后在复制Excel单元格组件后新增粘贴Excel列组件，填选相关参数，将复制的内容粘贴到F列。

![粘贴Excel列_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4456759161/p263575.png)

2. 流程运行后，程序将打开指定Excel文件，并在指定的Sheet页"Sheet1"上，复制A列的内容，随后将复制的内容及格式完全粘贴到F列。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![粘贴Excel列_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4456759161/p263576.png)



获取Excel的行数 
-------------------------------

**必要前置组件：** [获取当前激活的Sheet页](#section-qy3-3t0-rev) **\|** [创建Sheet页](#section-hos-4l4-bdc) **\|** [激活Sheet页](/cn.zh-CN/编辑器/可视化组件基本使用样例/EXCEL组件.md)

1. 使用"启动Excel"组件启动一个EXCEL文件，并使用"获取当前激活的Sheet页"组件获取要操作的sheet页，随后新增"获取Excel的行数"组件，在属性区填选已打开的Sheet对象，为了直观查看获取到的单元格的值，在此组件后新增记录日志组件，提示内容选择区域的值v_cell_row_cnt_1，完成后点击运行。

![获取Excel行数_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/4456759161/p263618.png)

2. 程序运行后，会打开对应的EXCEL文件，并统计有值的单元格行数，比如本例中对应sheet页上有3行数据，则通过"获取Excel的行数"组件将输出行数3。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![获取Excel行数_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/5456759161/p263628.png)



获取Excel的列数 
-------------------------------

**必要前置组件：** [获取当前激活的Sheet页](#section-qy3-3t0-rev) **\|** [创建Sheet页](#section-hos-4l4-bdc) **\|** [激活Sheet页](/cn.zh-CN/编辑器/可视化组件基本使用样例/EXCEL组件.md)

1. 使用"启动Excel"组件启动一个EXCEL文件，并使用"获取当前激活的Sheet页"组件获取要操作的sheet页，随后新增"获取Excel的列数"组件，在属性区填选已打开的Sheet对象，为了直观查看获取到的单元格的值，在此组件后新增记录日志组件，提示内容选择区域的值v_cell_column_cnt_1，完成后点击运行。

![获取Excel列数_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/5456759161/p263644.png)

2. 程序运行后，会打开对应的EXCEL文件，并统计有值的单元格列数，比如本例中对应sheet页上有4列数据，则通过"获取Excel的列数"组件将输出列数4。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![获取Excel列数_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/5456759161/p263651.png)



删除Excel行 
-----------------------------

**必要前置组件：** [获取当前激活的Sheet页](#section-qy3-3t0-rev) **\|** [创建Sheet页](#section-hos-4l4-bdc) **\|** [激活Sheet页](/cn.zh-CN/编辑器/可视化组件基本使用样例/EXCEL组件.md)

1. 使用"启动Excel"组件启动一个EXCEL文件，并使用"获取当前激活的Sheet页"组件获取要操作的sheet页，随后新增"删除Excel行"组件，在属性区填选已打开的Sheet对象，目标行号使用默认值1，完成后点击运行，将会模拟Excel操作，直接将第一行数据删除。

![删除Excel行_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/5456759161/p263669.png)![删除Excel行_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/5456759161/p263659.png)

2. 程序运行后，会打开对应的EXCEL文件，并删除第1行数据，后续行数据自动上移。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![删除Excel行_3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/5456759161/p263672.png)



删除Excel列 
-----------------------------

**必要前置组件：** [获取当前激活的Sheet页](#section-qy3-3t0-rev) **\|** [创建Sheet页](#section-hos-4l4-bdc) **\|** [激活Sheet页](/cn.zh-CN/编辑器/可视化组件基本使用样例/EXCEL组件.md)

1. 使用"启动Excel"组件启动一个EXCEL文件，并使用"获取当前激活的Sheet页"组件获取要操作的sheet页，随后新增"删除Excel列"组件，在属性区填选已打开的Sheet对象，目标列号使用默认值A，完成后点击运行，将会模拟Excel操作，直接将第A列数据删除。

![删除Excel列_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/5456759161/p263721.png)![删除Excel列_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/5456759161/p263726.png)

2. 程序运行后，会打开对应的EXCEL文件，并删除第A列数据，后续列数据自动左移。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![删除Excel列_3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/5456759161/p263728.png)



清除Excel区域 
------------------------------

**必要前置组件：** [获取当前激活的Sheet页](#section-qy3-3t0-rev) **\|** [创建Sheet页](#section-hos-4l4-bdc) **\|** [激活Sheet页](/cn.zh-CN/编辑器/可视化组件基本使用样例/EXCEL组件.md)

1. 使用"启动Excel"组件启动一个EXCEL文件，并使用"获取当前激活的Sheet页"组件获取要操作的sheet页，随后新增"清除Excel区域"组件，在属性区填选已打开的Sheet对象，目标起始行列号使用默认值1、A、2、B，完成后点击运行，将会模拟Excel操作，直接将第A1:B2区域的内容清除，默认也会清除对应区域的格式。

![清除Excel区域_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/5456759161/p263734.png)![清除Excel区域_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/5456759161/p263741.png)

2. 程序运行后，会打开对应的EXCEL文件，清除指定的A1:B2区域的数据，其他数据不变。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![清除Excel区域_3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6456759161/p263742.png)



插入Excel行 
-----------------------------

**必要前置组件：** [获取当前激活的Sheet页](#section-qy3-3t0-rev) **\|** [创建Sheet页](#section-hos-4l4-bdc) **\|** [激活Sheet页](/cn.zh-CN/编辑器/可视化组件基本使用样例/EXCEL组件.md)

1. 使用"启动Excel"组件启动一个EXCEL文件，并使用"获取当前激活的Sheet页"组件获取要操作的sheet页，随后新增"插入Excel行"组件，在属性区填选已打开的Sheet对象，目标行号使用默认值1，默认向目标行之前插入一行。

![插入Excel行_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6456759161/p263757.png)

2. 程序运行后，会打开对应的EXCEL文件，在原有数据第1行前插入1行。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![插入Excel行](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6456759161/p263765.png)



插入Excel列 
-----------------------------

**必要前置组件：** [获取当前激活的Sheet页](#section-qy3-3t0-rev) **\|** [创建Sheet页](#section-hos-4l4-bdc) **\|** [激活Sheet页](/cn.zh-CN/编辑器/可视化组件基本使用样例/EXCEL组件.md)

1. 使用"启动Excel"组件启动一个EXCEL文件，并使用"获取当前激活的Sheet页"组件获取要操作的sheet页，随后新增"插入Excel列"组件，在属性区填选已打开的Sheet对象，目标列号使用默认值A，默认向目标列之前插入一列。

![插入Excel列_1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6456759161/p263768.png)

2. 程序运行后，会打开对应的EXCEL文件，在原有数据第A列前插入1列。返回可视化操作界面，点击左下角日志面板，可参阅运行记录信息。

![插入Excel列_2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6456759161/p263770.png)
