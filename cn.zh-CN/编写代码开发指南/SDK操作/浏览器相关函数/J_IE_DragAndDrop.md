# J\_IE\_DragAndDrop {#concept_odk_rn5_zdb .concept}

拖拽到指定位置，规则如下

-   拖拽的起始位置为控件的中心点。
-   偏移量是相对于此控件的中心点来说的，如果向左拖，x轴偏移值应该是负数，如果向上拖，y轴偏移值应该是负数。

## 函数 {#section_d5h_5n5_zdb .section}

J\_IE\_DragAndDrop\(浏览器对象，MAP对象，控件对象，x偏移量，y偏移量\)

## 返回值 {#section_in4_5n5_zdb .section}

无

## 样例 {#section_jhd_wn5_zdb .section}

```

func test()
local $ie = J_IE_Catch("转账", "标题", "chrome")
local $array = J_IE("支付宝", "验>>", "获取坐标", "", $ie)
local $x1 = $array[1]
local $x2 = $array[3]
local $array2 = J_IE("支付宝", "验证域", "获取坐标", "", $ie)
local $lx2 = $array2[3]
;要拖的长度：
local $xoffset = $lx2 - ($x2 + $x1) / 2
j_log($xoffset)
local $result = J_IE_DragAndDrop($ie, "支付宝", "验>>", $xoffset)
if $result = 0 then
local $errorMsg = J_GetErrorMsg()
J_MsgBox($errorMsg)
endif
endfunc ;==>test
```

