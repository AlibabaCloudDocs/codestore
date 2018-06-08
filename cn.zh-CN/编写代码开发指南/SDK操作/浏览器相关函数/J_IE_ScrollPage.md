# J\_IE\_ScrollPage {#concept_flk_pwn_12b .concept}

让浏览器滚动一屏。

## 函数 {#section_y2v_qwn_12b .section}

J\_IE\_ScrollPage\(浏览器对象\)

## 返回值 {#section_cr1_rwn_12b .section}

-   1：其他
-   2：滚动条到底或滚动失败

## 样例 {#section_kyf_rwn_12b .section}

```

func test()
local $ie = J_IE_Catch("淘宝", "标题", 'chrome')
local $result
Do
$value = J_IE_ScrollPage($ie)
Until($value = 0)
endfunc ;==>test
```

