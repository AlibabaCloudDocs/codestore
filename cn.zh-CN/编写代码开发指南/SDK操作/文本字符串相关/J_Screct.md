# J\_Screct {#concept_hmd_cf4_12b .concept}

用于加密一段文本。

## 函数 {#section_m4m_df4_12b .section}

J\_Screct\(文本,\[模式:加密\]\)

## 返回值 {#section_jrt_df4_12b .section}

加密/解密后的文本。

## 样例 {#section_xjz_df4_12b .section}

```

Func Example41()
Local $string = "hello123456"
Local $screct1 = J_Screct($string, "加密")
J_MsgBox($screct1)
Local $screct2 = J_Screct($screct1, "解密")
J_MsgBox($screct2)
EndFunc ;==>Example41
```

