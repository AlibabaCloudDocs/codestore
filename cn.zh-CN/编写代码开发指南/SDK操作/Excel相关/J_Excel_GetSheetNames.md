# J\_Excel\_GetSheetNames {#concept_mx1_yh5_zdb .concept}

获取Excel表格中指定的Sheet个数和名称。

## 函数 {#section_hmx_zh5_zdb .section}

J\_Excel\_GetSheetNames\(Excel对象,序号=0\)

## 返回值 {#section_zqg_135_zdb .section}

-   序号为0的时候，返回sheet的个数。

-   当序号值大于0的时候，返回sheet所对应的名称。


## 样例 {#section_jwh_135_zdb .section}

```

Func Example50()
;定义一个局域变量$excel,用于保存打开的Excel表格对象。Excel表格打开后处于可见状态
Local $excel = J_Excel_Open("E:\数据.xlsx", "是")
;定义一个局域变量，用于保存$excel对象中Sheet的个数
Local $res = J_Excel_GetSheetNames($excel, 0)
;创建一个循环，从1到Sheet的最大值，用于遍历每一个Sheet的名字
For $i = 1 To $res
;定义一个局域变量$name,用于保存$i个Sheet的名字
Local $name = J_Excel_GetSheetNames($excel, $i)
;弹出一个提示框，显示当前是第几个sheet和sheet的名字
J_MsgBox($name, "第" & $i & "个")
Next
EndFunc ;==>Example50
```

