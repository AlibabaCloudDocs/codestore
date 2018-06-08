# J\_StringReplace {#concept_d5w_mg4_12b .concept}

将一个字符串中的一段文本替换成其他文本。

## 函数 {#section_lqg_zg4_12b .section}

J\_StringReplace\(总字符串,目标字符串,替换成的字符串\)

## 返回值 {#section_aqm_zg4_12b .section}

换后的字符串。

## 样例 {#section_ddv_zg4_12b .section}

```

Func Example34()
Local $text = "1122333"
;将文本$text中的文本22替换成文本8888
Local $new_text = J_StringReplace($text, "22", "8888")
J_MsgBox($new_text)
EndFunc ;==>Example34
```

