# J\_dialog {#concept_ip3_vkq_12b .concept}

js弹出窗口进行操作。

## 函数 {#section_qcj_xkq_12b .section}

J\_dialog\(\[“动作名称”\],\[按钮名称\],\[窗口标题\]\)

-   动作名称：点击/获取文本。

-   按钮名称：确定\(OK\)/取消\(Cancle\)


## 返回值 {#section_mrp_xkq_12b .section}

-   0：表示返回失败。

-   1：点击操作，表示成功。

-   对获取文本操作：返回值为相应的文本信息。


## 样例 {#section_acv_xkq_12b .section}

```

Func Example49()
local $text = J_dialog("获取文本")
;获取值为：请用j_dialog(点击)来关闭我
j_dialog("点击");点确定按钮
EndFunc ;==>Example49
```

