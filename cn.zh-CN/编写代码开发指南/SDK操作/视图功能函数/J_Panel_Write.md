# J\_Panel\_Write {#concept_c2v_qv4_12b .concept}

设置参数列表第几个或指定参数名的参数值。

## 函数 {#section_ev3_sv4_12b .section}

J\_Panel\_Write \(第几个/参数名,新值\)

## 返回值 {#section_mt4_sv4_12b .section}

1：设置成功

## 样例 {#section_nw5_sv4_12b .section}

```

Func Example19()
;在当前“我的应用”中参数列表中第2个参数设置文本"hello",此功能一般用于用户交互，可使用J_Panel_Read读取
J_Panel_Write(2, "hello")
;在当前“我的应用”中参数列表中参数“姓名”设置文本"叶子",此功能一般用于用户交互，可使用
J_Panel_Write("姓名","叶子")
EndFunc ;==>Example19
```

