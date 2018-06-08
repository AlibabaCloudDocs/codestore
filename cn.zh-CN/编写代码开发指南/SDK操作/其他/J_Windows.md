# J\_Windows {#concept_htn_2pq_12b .concept}

-   对窗口一系列操作,模式:激活/获取标题/获取文本/设置标题/隐藏/显示/关闭。

-   启用/禁用/最小化/最大化/透明/顶层/底层/闪烁/检测/等待出现/等待消失。

-   当模式为透明的时候,需要设置参数0-255,数字越小透明度越高。

-   当模式为设置标题的时候,参数表示新的标题名称。


## 函数 {#section_ckx_gpq_12b .section}

J\_Windows\(IE对象/窗口标题,\[模式:激活\],\[参数\]\)

## 返回值 {#section_y5d_hpq_12b .section}

-   获取标题：返回标题；

-   获取文本：返回页面全部可见文本；

-   设置标题/隐藏/显示/关闭/禁用/启用/最小化/最大化/透明/顶层/底层：成功1，失败0。


## 样例 {#section_dtl_hpq_12b .section}

```

Func Example48()
J_Windows("淘宝网", "激活")
Local $title = J_Windows("淘宝网", "获取标题")
Local $text = J_Windows("淘宝网", "获取文本")
J_Windows("淘宝网", "设置标题", "我爱淘宝网")
J_Windows("淘宝网", "隐藏")
J_Windows("淘宝网", "显示")
J_Windows("淘宝网", "关闭")
J_Windows("淘宝网", "禁用")
J_Windows("淘宝网", "启用")
J_Windows("淘宝网", "最小化")
J_Windows("淘宝网", "最大化")
;透明度0-255越大越不透明
J_Windows("淘宝网", "透明", 100)
J_Windows("淘宝网", "顶层")
J_Windows("淘宝网", "底层")
J_Windows("淘宝网", "闪烁")
Local $res = J_Windows("淘宝网", "检测")
If $res = 1 Then
J_MsgBox("检测到了~")
Else
J_MsgBox("没检测到~")
EndIf
Local $res = J_Windows("淘宝网", "等待出现", 3)
If $res = 1 Then
J_MsgBox("3秒内出现了~")
Else
J_MsgBox("3秒内没出现~")
EndIf
Local $res = J_Windows("淘宝网", "等待消失", 8)
If $res = 1 Then
J_MsgBox("8秒内消失了~")
Else
J_MsgBox("8秒内没消失~")
EndIf
EndFunc ;==>Example48
```

