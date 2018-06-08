# J\_EXP {#concept_dsy_424_12b .concept}

通过正则表达式获得指定的文本。

## 函数 {#section_n3b_r24_12b .section}

J\_EXP\(总字符串,正则表达式,\[位置:1\]\)

## 返回值 {#section_cyh_r24_12b .section}

当位置等于0的时候返回值为1或者0，代表是否符合此正则表达式。

## 样例 {#section_iyn_r24_12b .section}

```

Func Example35()
;声明一个名为$string的局域变量，保存文本 "hello1234hi4567good7890"
Local $string = "hello1234hi4567good7890"
;方法1,优点，速度快，一般用于批量提取
;声明一个名为$open的局域变量，保存从文本$string中提取满足正则表达式的数据集合
Local $open = J_EXP_Open($string, "\d+")
;声明一个名为$max的局域变量，保存$open数据集合中的数据个数
Local $max = J_EXP_MaxCount($open, "\d+")
;创建一个循环，从1开始遍历这个集合
For $i = 1 To $max Step 1
;声明一个名为$sub_string的局域变量，保存逐个取出集合open中的数据
Local $sub_string = J_EXP($open, "\d+", $i)
;通过系统提示框的形式显示出$sub_string里装载的数据
J_MsgBox($sub_string, $i)
Next
;方法2，优点，简单，一般用于单条提取
;声明一个名为$sub_string2的局域变量，保存文本$string中满足正则表达式\d+的第6个数据
Local $sub_string2 = J_EXP($string, "\d+", 6)
J_MsgBox($sub_string2)
;用于判断是否满足正则表达式,第三个参数（位置）必须为0
Local $result = J_EXP($string, "\w+\d+", 0)
If $result = 1 Then
J_MsgBox("满足正则表达式\w+\d+")
Else
J_MsgBox("不满足正则表达式\w+\d+")
EndIf
EndFunc ;==>Example35
```

