# J\_Date\_Diff {#concept_osr_hf5_zdb .concept}

返回两个日期的不同，使用指定类型表达。

## 函数 {#section_s1l_jf5_zdb .section}

J\_Date\_Diff\(开始日期,结束日期\[,模式:日\]\)

-   开始日期：指定开始日期；
-   结束日期：指定结束日期；
-   模式：年/Y 月/M 日/D 时/H 分/N 秒/S，建议使用英文。

## 返回值 {#section_k25_jf5_zdb .section}

返回两个日期间隔的数字。

## 样例 {#section_nz2_kf5_zdb .section}

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

