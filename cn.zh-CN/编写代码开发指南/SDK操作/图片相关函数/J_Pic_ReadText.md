# J\_Pic\_ReadText {#concept_inv_xyn_12b .concept}

抓取图片上的文字，可以是url地址或者是本地路径。

## 函数 {#section_ulj_zyn_12b .section}

J\_Pic\_ReadText\(图片路径/图片地址\)

## 返回值 {#section_xjq_zyn_12b .section}

图片上的文字，如果返回值为\[OCR:Error\]那么证明图片识别失败。

## 样例 {#section_nqz_zyn_12b .section}

```

Func Example33()
;声明一个名为$path1的局域变量，保存文本 "D:\1.jpg"
Local $path1 = "D:\1.jpg"
;声明一个名为$path2的局域变量，保存文本 "http://img04.taobaocdn.com/bao/uploaded/i4/T1h8VkFX8XXXb1upjX.jpg"
Local $path2 = "http://img04.taobaocdn.com/bao/uploaded/i4/T1h8VkFX8XXXb1upjX.jpg"
;使用此功能需要电脑装有相应插件
;声明一个名为$value1的局域变量，保存从$path1路径的图片中提取的中文文本
Local $value1 = J_Pic_ReadText($path1, "中文")
;声明一个名为$value2的局域变量，保存从$path2路径的图片中提取的英文文本
Local $value2 = J_Pic_ReadText($path2, "英文")
;以系统信息提示框的形式显示出$value1保存的数据
J_MsgBox($value1)
;以系统信息提示框的形式显示出$value2保存的数据
J_MsgBox($value2)
EndFunc ;==>Example33
```

