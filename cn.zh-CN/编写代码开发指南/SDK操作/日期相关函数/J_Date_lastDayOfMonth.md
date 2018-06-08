# J\_Date\_lastDayOfMonth {#concept_zyf_4f5_zdb .concept}

获取某日期所在月份的最后一天。

## 函数 {#section_mjn_wf5_zdb .section}

J\_Date\_lastDayOfMonth\(\[日期:系统时间\]\)

**说明：** 默认值为当前日期。

## 返回值 {#section_u45_wf5_zdb .section}

某日期所在月份的最后一天。

## 样例 {#section_uc1_xf5_zdb .section}

```

Func Example34()
;取当前月份的最后一天
j_msgbox(J_Date_lastDayOfMonth())
;取2017-04月的最的一天
j_msgbox(j_date_lastDayOfMonth('2017-04'))
j_msgbox(j_date_lastDayOfMonth('2017-04-08'))
EndFunc ;==>Example34
```

