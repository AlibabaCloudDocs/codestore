# J\_IE\_Catch {#concept_hy4_mm5_zdb .concept}

捕获已打开的浏览器对象，模式为：标题、地址、子窗口。

## 函数 {#section_vly_nm5_zdb .section}

J\_IE\_Catch\(字符串,抓取模式\)

## 返回值 {#section_ynf_4m5_zdb .section}

成功返回浏览器对象，失败返回0。

## 样例 {#section_blm_4m5_zdb .section}

```

Func Example27()
;声明一个名为$ie的局域变量，将通过浏览器窗口标题“淘宝网”获取浏览器对象保存这个变量中
Local $ie = J_IE_Catch("淘宝网", "标题")
;声明一个名为$ie2的局域变量，将通过浏览器URL地址www.taobao.com获取浏览器对象保存这个变量中
Local $ie2 = J_IE_Catch("www.taobao.com", "地址")
;如果要抓chrome浏览器对象:注意，catch的窗口必须是通过程序打开出来的chrome窗口，可以用J_IE_Create
local $ie3 = J_IE_Catch("www.taobao.com","地址","Chrome")
EndFunc ;==>Example27
```

