# J\_Excel\_Save {#concept_fmr_lj5_zdb .concept}

保存或者另存当前Excel文件，当不输入另存路径的时候就是保存当前已打开的Excel。

## 函数 {#section_wy4_nj5_zdb .section}

J\_Excel\_Save\(Excel对象,\[另存路径\]\)

## 返回值 {#section_pmw_nj5_zdb .section}

成功返回1，失败返回0。

## 样例 {#section_hmg_4j5_zdb .section}

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
EndFunc ;==>Example38
```

