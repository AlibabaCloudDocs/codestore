# J\_IE\_GetScrollTop {#concept_w3g_5vn_12b .concept}

获取浏览器滚动条高度。

## 函数 {#section_tmx_vvn_12b .section}

J\_IE\_GetScrollTop\(浏览器对象\)

## 返回值 {#section_tyf_wvn_12b .section}

获取滚动条高度。

## 样例 {#section_hzl_wvn_12b .section}

```

func test()
local $ie = j_ie_create("www.taobao.com",default,default,default,"chrome")
;滚一屏
J_IE_ScrollPage($ie)
local $top = J_IE_GetScrollTop($ie)
j_msgbox($top)
endfunc
```

