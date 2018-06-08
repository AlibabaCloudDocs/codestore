# J\_IE\_Text {#concept_idn_kyn_12b .concept}

获得IE浏览器上的全部文本。

## 函数 {#section_xcy_lyn_12b .section}

J\_IE\_Text\(IE对象\)

## 返回值 {#section_mcf_myn_12b .section}

获得IE浏览器上的全部文本。

## 样例 {#section_ogk_myn_12b .section}

```

Func Example25()
;新建一个IE窗口并打开www.crm.admin.com链接,声明一个名为$ie的局域变量，装入这个新创建浏览器的对象
Local $ie = J_IE_Create("www.taobao.com")
;声明 $text的一个局域变量，将$ie对应的浏览器对象获取页面所有可见文本，并将其保存至此变量中
Local $text = J_IE_Text($ie)
;信息提示窗口显示出变量$text中保存的全部文本
J_MsgBox($text)
EndFunc ;==>Example25
```

