# J\_Date\_trunc {#concept_fxw_hg5_zdb .concept}

获取日期中的信息，如年、月、日。

## 函数 {#section_ex5_jg5_zdb .section}

J\_Date\_trunc\(日期\[,模式:日\]\)

模式可选值：日/天/年/月/时/分/秒

## 返回值 {#section_gkb_kg5_zdb .section}

反馈指定日期和模式的信息。

## 样例 {#section_x33_kg5_zdb .section}

```

Func Example36()
j_msgbox(j_date_trunc('2015-01-05', '年'))
j_msgbox(j_date_trunc('2015-01-05 12:34:09', '月'))
j_msgbox(j_date_trunc('2015-01-05 12:34:09', '天'))
j_msgbox(j_date_trunc('2015-01-05', '时'))
j_msgbox(j_date_trunc('2015-01-05 12:34:09', '时'))
j_msgbox(j_date_trunc('2015-01-05 12:34:09', '分'))
j_msgbox(j_date_trunc('2015-01-05 12:34:09', '秒'))
EndFunc ;==>Example36
```

