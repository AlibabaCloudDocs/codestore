# J\_MsgBox {#concept_kbp_gnq_12b .concept}

显示一个消息窗口。

按钮个数默认为1个，可以修改成2。

## 函数 {#section_n3t_3nq_12b .section}

J\_MsgBox\(\[“窗口文本”\],\[“标题”\],\[是否顶层:是\],\[按钮个数:1\]\)

## 返回值 {#section_dfb_jnq_12b .section}

-   单击**确定**，返回值为1。

-   单击**取消**，返回值为2


## 样例 {#section_lxk_jnq_12b .section}

```

Func Example49()
;作用1:显示一个消息窗口。按钮个数默认为1个，可以修改成2，当点击确定之后返回值为1,点击取消返回值为2
J_MsgBox("用来信息提示")
J_MsgBox("带标题的提示", "标题")
J_MsgBox("带标题的底层的提示", "标题", "否")
Local $sel = J_MsgBox("确认或者取消", "标题", "是", 2)
If $sel = 0 Then
J_MsgBox("你啥按钮也没点")
EndIf
If $sel = 1 Then
J_MsgBox("你点了确定按钮")
EndIf
If $sel = 2 Then
J_MsgBox("你点了取消按钮")
EndIf
EndFunc ;==>Example49
```

