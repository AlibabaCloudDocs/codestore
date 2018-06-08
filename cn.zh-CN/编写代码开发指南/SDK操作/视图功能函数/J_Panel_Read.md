# J\_Panel\_Read {#concept_crg_gv4_12b .concept}

获得码栈参数列表中的某一行值或指定某个参数名的值。

## 函数 {#section_tqj_mv4_12b .section}

J\_Panel\_Read \(第几个/参数名\)

## 返回值 {#section_cfr_mv4_12b .section}

返回相应参数值。

## 样例 {#section_tqw_mv4_12b .section}

```

Func Example20()
;声明 $result1的一个局域变量，并将当前“我的应用”中参数列表中第2个的数据保存至整个变量中
Local $result = J_Panel_Read(2)
;将当前“我的应用”参数列表中参数名“旺旺发送内容”的数据保存到$result2变量中
local $result2 = J_Panel_Read("旺旺发送内容")
EndFunc ;==>Example20
```

