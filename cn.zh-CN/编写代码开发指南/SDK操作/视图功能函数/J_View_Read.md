# J\_View\_Read {#concept_k5b_4x4_12b .concept}

获取数据列表中的数据。

## 函数 {#section_q13_px4_12b .section}

J\_View\_Read \(行号,列号/列名称\)

## 返回值 {#section_k2g_qx4_12b .section}

返回指定列表中的数据。

## 样例 {#section_vcn_qx4_12b .section}

```

Func Example11()
;声明 $result的一个局域变量，读取当前“我的应用”中数据列表的第1行第1列单元格中的数据，并将读取的数据保存在这个变量中
Local $result = J_View_Read(1, 1)
;读取当前“我的应用”中数据列表的第1行列名为“部门”单元格中的数据，并将读取的数据保存在这个变量中
local $result2 = J_View_Read(1, "部门")
EndFunc ;==>Example11
```

