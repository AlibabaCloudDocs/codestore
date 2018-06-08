# J\_IE\_Link {#concept_xtw_jwn_12b .concept}

通过已知浏览器打开一个链接。

## 函数 {#section_wp3_lwn_12b .section}

J\_IE\_Link\(IE对象,链接地址,\[是否等待:是\]\)

## 返回值 {#section_h1p_lwn_12b .section}

浏览器对象

## 样例 {#section_wwt_lwn_12b .section}

```

Func Example24()
;新建一个IE窗口并打开www.taobao.com链接,声明一个名为$ie的局域变量，装入这个新创建浏览器的对象
Local $ie = J_IE_Create("www.taobao.com")
;通过变量$ie中保存的浏览器对象所对应的浏览器打开新的链接地址ju.taobao.com
J_IE_Link($ie, "ju.taobao.com")
EndFunc ;==>Example24
```

