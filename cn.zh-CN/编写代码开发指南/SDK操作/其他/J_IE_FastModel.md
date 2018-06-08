# J\_IE\_FastModel {#concept_wwc_zlq_12b .concept}

IE浏览器模式切换：

-   1:快捷模式。

-   0:普通模式。


默认为普通模式。

## 函数 {#section_vkz_1mq_12b .section}

J\_IE\_FastModel\(\[模式:0\]\)

## 返回值 {#section_gtf_bmq_12b .section}

无。

## 样例 {#section_kjn_bmq_12b .section}

```

Func Example45()
;E浏览器模式切换,1:快捷模式，0:普通模式,默认为普通模式,注意快捷模式不显示图片,如果影响用户使用需要将参数设置为0再执行一次
J_IE_FastModel(1)
Local $ie = J_IE_Create("www.taobao.com")
Sleep(2000)
J_IE_Close($ie)
J_IE_FastModel(0)
Local $ie2 = J_IE_Create("www.taobao.com")
Sleep(2000)
J_IE_Close($ie2)
EndFunc ;==>Example45
```

