# J\_EXP\_MaxCount {#concept_rpg_ql5_zdb .concept}

返回满足此正则表达式匹配的个数。

## 函数 {#section_ny1_sl5_zdb .section}

J\_EXP\_MaxCount\(总字符串,正则表达式\)

## 返回值 {#section_yxh_sl5_zdb .section}

返回满足此正则表达式匹配的个数。

## 样例 {#section_af4_sl5_zdb .section}

```

Func Example28()
;声明一个名为$ie的局域变量，将通过浏览器窗口标题“淘宝网”获取浏览器对象保存这个变量中
Local $ie = J_IE_Catch("淘宝网", "标题")
;注意J_IE_EXP_MaxCount必须要配合控件录制工具使用
;声明 $max的一个局域变量，在$ie变量中对应的浏览器页面中检索，对应的控件相同属性的在页面中一共有多少个，并保存至$max变量中
;一般情况下用于循环或者判断
Local $max = J_IE_EXP_MaxCount($ie, "淘宝网", "搜索框exp")
;创建一个循环，从1开始$max中保存的数字截止，注意，如果没写step的话步长默认为1
For $i = 1 To $max
;声明 $result的一个局域变量，在$ie变量中对应的浏览器页面对应的第$i个控件执行输入hello的操作，并将结果保存至$result变量中(执行成功1，执行失败0)
Local $result = J_IE_EXP("淘宝网", "搜索框exp", $i, "输入", "hello", $ie)
;下一次循环
Next
EndFunc ;==>Example28
```

