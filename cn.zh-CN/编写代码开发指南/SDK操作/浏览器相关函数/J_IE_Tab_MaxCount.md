# J\_IE\_Tab\_MaxCount {#concept_tnq_zxn_12b .concept}

获得IE表格一共多少行。

## 函数 {#section_ofz_1yn_12b .section}

J\_IE\_Tab\_MaxCount\(表格对象\)

## 返回值 {#section_rn2_byn_12b .section}

获得IE表格一共多少行。

## 样例 {#section_isj_byn_12b .section}

```

Func Example30()
;声明一个名为$ie的局域变量，将通过浏览器窗口标题“淘宝TSP”获取浏览器对象保存这个变量中
Local $ie = J_IE_Catch("淘宝TSP", "标题")
;声明一个名为$tab的局域变量，在变量$ie对应的浏览器页面中通过表格可见文本的正则表达式定位表格，并将表格文本对象保存至变量$tab中
Local $tab = J_IE_Tab_FindByText($ie, "买家真实姓名", "文本")
;声明一个名为$tab2的局域变量，在变量$ie对应的浏览器页面中通过表格的内嵌HTML代码的正则表达式定位表格，并将表格html代码对象保存至变量$tab中
Local $tab2 = J_IE_Tab_FindByHtml($ie, "Example30
```

