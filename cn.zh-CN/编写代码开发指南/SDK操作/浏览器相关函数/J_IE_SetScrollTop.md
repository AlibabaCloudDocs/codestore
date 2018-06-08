# J\_IE\_SetScrollTop {#concept_srd_wwn_12b .concept}

设置浏览器滚动条高度。

## 函数 {#section_jqr_xwn_12b .section}

J\_IE\_SetScrollTop\(浏览器对象，滚动条高度\)

## 返回值 {#section_adx_xwn_12b .section}

-   1：成功
-   0：失败

## 样例 {#section_f2c_ywn_12b .section}

```

func test()
local $ie = J_IE_Catch("淘宝", "标题", 'chrome')
J_IE_SetScrollTop($ie, 300)
endfunc
```

