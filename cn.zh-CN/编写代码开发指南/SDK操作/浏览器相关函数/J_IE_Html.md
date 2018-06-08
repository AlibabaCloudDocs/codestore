# J\_IE\_Html {#concept_fdd_2wn_12b .concept}

获得IE浏览器上的全部Html代码。

## 函数 {#section_qtp_fwn_12b .section}

J\_IE\_Html\(IE对象\)

## 返回值 {#section_ivx_fwn_12b .section}

IE浏览器上的全部Html代码。

## 样例 {#section_rqc_gwn_12b .section}

```

Func Example26()
;新建一个IE窗口并打开www.crm.admin.com链接,声明一个名为$ie的局域变量，装入这个新创建浏览器的对象
Local $ie = J_IE_Create("www.taobao.com")
;声明 $html的一个局域变量，获取$ie对应的浏览器对象获取页面所有渲染的代码，并将其保存至此变量中
Local $html = J_IE_Html($ie)
;信息提示窗口显示出变量$text中保存的全部文本
J_MsgBox($html)
EndFunc ;==>Example26
```

