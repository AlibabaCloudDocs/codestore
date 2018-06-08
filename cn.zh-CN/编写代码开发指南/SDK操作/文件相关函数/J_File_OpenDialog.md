# J\_File\_OpenDialog {#concept_gsq_qk5_zdb .concept}

用于弹出一个文件选择窗口。

## 函数 {#section_ccg_sk5_zdb .section}

J\_File\_OpenDialog\(\[标题默认:请选择文件\]\)

## 返回值 {#section_wlm_sk5_zdb .section}

用户选择文件的路径。

## 样例 {#section_ovr_sk5_zdb .section}

```

Func Example31()
;声明一个名为$filepath的局域变量，创建一个文件选择对话框，用户可以选择文件，返回选择的文件路径，并将此路径保存至$filepath变量中
Local $filepath = J_File_OpenDialog()
;声明一个名为$max的局域变量，将$filepath文件里面内容行数保存至这个变量中
Local $max = J_File_MaxCount($filepath)
;创建一个循环，从1到$max
For $i = 1 To $max
;声明一个名为$nr的局域变量，将$filepath文件里面第$i行的内容保存至这个变量中
Local $nr = J_File_Read($filepath, $i)
;@crlf的意思是换行符，另起一行
;通过系统信息提示框显示拼凑的文本
J_MsgBox("第" & $i & "行" & @CRLF & $nr)
;下一次循环
Next
;当读取文件内容第几行设置为0的时候，此函数会读取文件中的全部文本
Local $alltext = J_File_Read($filepath, 0)
J_MsgBox($alltext)
;向文件尾部追加数据
J_File_Write($filepath, "追加一条数据", "追加")
Local $alltext = J_File_Read($filepath, 0)
;校验追加的数据是否成功
J_MsgBox($alltext)
;把文件的数据替换掉
J_File_Write($filepath, "覆盖过后的数据", "覆盖")
Local $alltext = J_File_Read($filepath, 0)
;校验覆盖的数据是否成功
J_MsgBox($alltext)
EndFunc ;==>Example31
```

