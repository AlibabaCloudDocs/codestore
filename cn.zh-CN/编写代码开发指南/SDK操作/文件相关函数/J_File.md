# J\_File {#concept_qgl_ck5_zdb .concept}

文件的一些基础操作，动作可选值：

-   文件操作：新建文件/删除文件/复制文件/移动文件/文件改名/获取文件大小。
-   文件夹操作：新建文件夹/删除文件夹/复制文件夹/移动文件夹/文件夹改名/获取文件夹大小。

## 函数 {#section_ynj_2k5_zdb .section}

J\_File\(文件\(夹\)路径,动作,值\)

## 返回值 {#section_w4x_2k5_zdb .section}

-   0：成功
-   1：失败

## 样例 {#section_x3g_fk5_zdb .section}

```

func Example47()
;文件夹操作：
local $path = 'D:\file\测试文件'
local $res = J_File($path,"是否存在")
;新建
if $res = 0 then
J_File($path,"新建文件夹")
EndIf
;移动
J_File($path,"移动文件夹","C:\file\测试文件")
;复制
J_File("C:\file\测试文件","复制文件夹","D:\file\测试文件new")
;改名
J_File("D:\file\测试文件new","文件夹改名","D:\file\测试文件rename")
;文件夹大小
local $size = J_File("D:\code","获取文件夹大小")
Msgbox(0,"","大小(MB) :" & Round($size / 1024 / 1024))
;删除文件夹
J_File("D:\nw2","删除文件夹")
;文件操作：
local $filepath = 'D:\file\测试文件rename\11.txt'
$res = J_File($filepath,"是否存在")
;新建
if $res = 0 then
J_File($filepath,"新建文件")
EndIf
;写值
J_File_Write($filepath,'你好，码栈',"追加")
;获取大小
local $size = J_File($filepath,"获取文件大小")
j_msgbox("文件大小：字节" & $size)
;移动:将文件移动到目录：C:\file\测试文件下
J_File($filepath,"移动文件","C:\file\测试文件")
;复制:将文件复制到目录:D:\file下
J_File($filepath,"复制文件","D:\file")
;改名
J_File($filepath,"文件改名","C:\file\测试文件\22.txt")
;删除文件
J_File($filepath,"删除文件")
endfunc; ==>
```

