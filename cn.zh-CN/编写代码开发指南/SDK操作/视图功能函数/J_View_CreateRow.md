# J\_View\_CreateRow {#concept_z3m_jw4_12b .concept}

在数据列表中创建一条新数据。

## 函数 {#section_wlg_lw4_12b .section}

J\_View\_CreateRow \(新值\)

## 返回值 {#section_ig4_lw4_12b .section}

返回值为新创建数据的行数。

## 样例 {#section_obt_lw4_12b .section}

```

Func Example12()
;声明 $index的一个局域变量，在当前“我的应用”中数据列表中最后追加一条数据并在这条数据的第1列设置文本“你好，世界”，并将新追加的数据的行号保存在这个变量中
Local $index = J_View_CreateRow("你好，世界")
EndFunc ;==>Example12
```

