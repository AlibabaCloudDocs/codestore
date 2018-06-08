# J\_View\_GetRowChecked {#concept_svz_5w4_12b .concept}

获取数据列表中某行数据是否为勾选状态。

## 函数 {#section_wrr_ww4_12b .section}

J\_View\_GetRowChecked \(行号\)

## 返回值 {#section_ctx_ww4_12b .section}

-   True：在码栈中True=1
-   False：在码栈中False=0

## 样例 {#section_otc_xw4_12b .section}

```

Func Example15()
;声明 $result的一个局域变量，获取当前“我的应用”中数据列表中第20行数据的勾选状态，并将结果保存在这个变量中（勾选状态值为1，未勾选状态值为0）
Local $result = J_View_GetRowChecked(20)
EndFunc ;==>Example15
```

