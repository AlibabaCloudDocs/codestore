# J\_View\_Write {#concept_lkh_3y4_12b .concept}

设置数据列表中的数据。

## 函数 {#section_o2z_jy4_12b .section}

J\_View\_Write \(行号,列号/列名称,设置值\)

## 返回值 {#section_ft2_ky4_12b .section}

-   1：设置成功
-   0：设置失败

## 样例 {#section_njk_ky4_12b .section}

```

Func Example10()
;声明 $result的一个局域变量，将当前“我的应用”中数据列表的第1行第1列单元格设置文本“hello”，并将插入数据的结果保存在这个变量中
Local $result = J_View_Write(1, 1, "Hello")
;将当前“我的应用”中数据列表的第1行列名为“部门”单元格设置文本“hello”，并将插入数据的结果保存在这个变量中
Local $result2 = J_View_Write(1, "部门", "Hello")
EndFunc ;==>Example10
```

