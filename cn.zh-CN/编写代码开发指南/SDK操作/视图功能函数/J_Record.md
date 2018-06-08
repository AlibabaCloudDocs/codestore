# J\_Record {#concept_mqq_wv4_12b .concept}

用于累加记录用户成功执行的自动化数据，每执行成功一次调用一次这个函数即可。

## 函数 {#section_kzk_zv4_12b .section}

J\_Record\(\)

## 返回值 {#section_pdt_zv4_12b .section}

无

## 样例 {#section_igy_zv4_12b .section}

```

Func Example42()
;获取当前“我的应用”中视图数据的行数
Local $max = J_View_MaxCount()
;创建一个循环用来变遍历每一行数据
For $i = 1 To $max
;if语句的特殊用法，当if语句中只有一个执行的表达式，那么if语句可以和判断之后的内容写在一行
If J_View_GetRowChecked($i) = 0 Then ContinueLoop
;用来记录用，注意，提交的发布的工具必须要使用此功能
;调用一次J_Record那么代表此工具执行了一条数据，此功能非常重要！！！！
J_Record()
Next
EndFunc ;==>Example42
```

