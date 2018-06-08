# J\_Date\_Add {#concept_tz4_s25_zdb .concept}

计算一个指定的日期和间隔后的新日期，时间格式为:YYYY-MM-DD。

## 函数 {#section_x1s_525_zdb .section}

J\_Date\_Add\(日期,要添加的数量,\[模式:日\]\)

-   日期：指定日期；
-   要添加的数量：可以是正数也可以是负数；
-   模式：模式:年/Y 月/M 日/D 时/H 分/N 秒/S。

## 返回值 {#section_w31_w25_zdb .section}

计算后的日期，格式为：YYYY-MM-DD。

## 样例 {#section_k4c_x25_zdb .section}

```

Func Example32()
;声明一个名为$d1的局域变量，保存日期格式的文本"2016-03-04 23:00:35"
Local $d1 = "2016-03-04 23:00:35"
;声明一个名为$d2的局域变量，保存日期格式的文本"2016-03-05 06:07:09"
Local $d2 = "2016-03-05 06:07:09"
;声明一个名为$d3的局域变量，保存日期格式的文本"2016-03-06 14:50:21"
Local $d3 = "2016-03-06 14:50:21"
;声明一个名为$d4的局域变量，保存在日期$d1的基础上后退3天(D)
Local $d4 = J_Date_Add($d1, 3, "D")
;$d2和$d3相差多少个小时(H)
Local $diff = J_Date_Diff($d2, $d3, "H")
;以系统信息提示框的形式显示出$d4保存的数据
J_MsgBox($d4)
;以系统信息提示框的形式显示出$diff保存的数据
J_MsgBox($diff)
EndFunc ;==>Example32
```

