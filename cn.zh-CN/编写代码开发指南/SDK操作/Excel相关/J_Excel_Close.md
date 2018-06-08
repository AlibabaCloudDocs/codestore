# J\_Excel\_Close {#concept_khj_rg5_zdb .concept}

关闭Excel。

## 函数 {#section_rnb_tg5_zdb .section}

J\_Excel\_Close\(Excel对象, \[默认保存:是\]\)

## 返回值 {#section_k53_tg5_zdb .section}

成功返回1，失败返回0。

## 样例 {#section_ocs_tg5_zdb .section}

```

Func Example38()
;新创建一个Excel，可见
Local $excel1 = J_Excel_Create("是")
;在后台打开Excel，不可见
Local $excel2 = J_Excel_Open("D:\1.xlsx", "否")
J_Excel_Write($excel1, 1, 1, "hello", "new_sheet")
;Excel表格一共有多少行
Local $maxrow = J_Excel_MaxCount($excel2, "sheet1")
;Excel中一共有多少列
Local $maxcol = J_Excel_MaxCol($excel2, "sheet1")
;拷贝数据，从1行1列到最大行最大列
J_Excel_CopySell($excel2, 1, 1, $maxrow, $maxcol, "sheet1")
;粘贴数据
J_Excel_PasteSell($excel1, 1, 1, "new2_sheet")
;读取Excel1中new2_sheet中的第2行第3列
Local $string = J_Excel_Read($excel1, 2, 3, "new2_sheet")
;信息框显示出读取的数据
J_MsgBox($string)
;删除Excel1的sheet1
J_Excel_DeleteSheet($excel1, "sheet1")
;将Excel1保存至D:\2.xlsx
J_Excel_Save($excel1, "D:\2.xlsx")
;关闭Excel1，保存
J_Excel_Close($excel1)
;关闭Excel2，不保存
J_Excel_Close($excel2, "否")
EndFunc ;==>Example38g", "D:\5.jpg", 700, 1000)
EndFunc ;==>Example40
```

