# J\_GetErrorMsg {#concept_amb_slq_12b .concept}

获取异常信息，用于展示执行过程中的异常或失败的原因。

## 函数 {#section_lpf_5lq_12b .section}

无。

## 返回值 {#section_ydm_5lq_12b .section}

无。

## 样例 {#section_fsr_5lq_12b .section}

```

Func Example49()
local $result= J_dialog("点击")
;有两种方式，处理失败的情况
local $errorMsg
;方式一：
if @error then
$errorMsg = J_GetErrorMsg()
endif
;方式二：
if $result = 0 then
$errorMsg = J_GetErrorMsg()
EndIf
EndFunc ;==>Example49
```

