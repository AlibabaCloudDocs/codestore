# J\_View\_SetRowChecked {#concept_ecb_5x4_12b .concept}

设置码栈数据列表中的某行勾选状态为勾选。

## 函数 {#section_qnn_vx4_12b .section}

J\_View\_SetRowChecked \(行号,\[勾选状态:是/否\]\)

## 返回值 {#section_a1v_vx4_12b .section}

-   1：设置成功
-   0：设置失败

## 样例 {#section_ftz_vx4_12b .section}

```

Func Example16()
;声明 $result1的一个局域变量，设置当前“我的应用”中数据列表中第5行数据的勾选状态为勾选状态，并将结果保存在这个变量中（结果一定是1）
Local $result1 = J_View_SetRowChecked(5, "是")
;声明 $result1的一个局域变量，设置当前“我的应用”中数据列表中第6行数据的勾选状态为未勾选状态，并将结果保存在这个变量中（结果一定是1）
Local $result2 = J_View_SetRowChecked(6, "否")
EndFunc ;==>Example16
```

