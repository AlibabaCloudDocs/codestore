# J\_Select {#concept_ey3_m4q_12b .concept}

提供用户备选选项选择框,多个备选值用”|“分隔，能否修改，是否支持用户键盘输入，默认不支持0,1支持。

## 函数 {#section_a5h_44q_12b .section}

J\_Select\(标题,提示信息,默认值,备选值,\[能否修改:默认:0/1\],\[X坐标:中间\],\[Y坐标:中间\]\)

## 返回值 {#section_tc4_44q_12b .section}

无。

## 样例 {#section_g1w_44q_12b .section}

```

Func Example47()
Local $sel = J_Select("码栈", "请选择您的部门", "聚划算", "淘宝网|聚划算|1688|菜鸟|蚂蚁金服")
J_MsgBox("您选择了部门:" & $sel)
EndFunc ;==>Example47
```

