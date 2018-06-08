# J\_IE\_Tab\_FindByHtml {#concept_ndh_3xn_12b .concept}

通过html正则表达式获取表格对象，模式为文本或者html。

## 函数 {#section_zhn_kxn_12b .section}

J\_IE\_Tab\_FindByHtml\(IE对象,正则表达式,\[模式:文本\]\)

## 返回值 {#section_rmw_kxn_12b .section}

成功返回表格对象，失败返回0。

## 样例 {#section_ccc_lxn_12b .section}

```

Func Example30()
;声明一个名为$ie的局域变量，将通过浏览器窗口标题“淘宝TSP”获取浏览器对象保存这个变量中
Local $ie = J_IE_Catch("淘宝TSP", "标题")
;声明一个名为$tab的局域变量，在变量$ie对应的浏览器页面中通过表格可见文本的正则表达式定位表格，并将表格文本对象保存至变量$tab中
Local $tab = J_IE_Tab_FindByText($ie, "买家真实姓名", "文本")
;声明一个名为$tab2的局域变量，在变量$ie对应的浏览器页面中通过表格的内嵌HTML代码的正则表达式定位表格，并将表格html代码对象保存至变量$tab中
Local $tab2 = J_IE_Tab_FindByHtml($ie, "Example30
```

