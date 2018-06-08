# J\_Date\_sysDate {#concept_thm_bg5_zdb .concept}

根据格式，返回特定格式的当前系统时间。

## 函数 {#section_qd3_dg5_zdb .section}

J\_Date\_sysDate\(\[格式:yyyy-mm-dd hh:mm:ss\]\)

## 返回值 {#section_kvt_dg5_zdb .section}

特定格式的当前时间，默认格式是 yyyy-mm-dd hh:mm:ss。

## 样例 {#section_ss1_2g5_zdb .section}

```

Func Example33()
;取当年月日
j_msgbox(J_Date_sysDate('yyyy-mm-dd'))
;取年月日 时分秒
j_msgbox(J_Date_sysDate('yyyy-mm-dd hh:mi:ss'))
;另一种格式
j_msgbox(J_Date_sysDate('yyyy/mm/dd hh:mi:ss'))
EndFunc ;==>Example33
```

