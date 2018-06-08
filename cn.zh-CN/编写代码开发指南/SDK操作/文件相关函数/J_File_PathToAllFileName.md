# J\_File\_PathToAllFileName {#concept_ays_wk5_zdb .concept}

获得文件夹下面全部的文件名称集合，可以配合J\_EXP系列函数使用。

## 函数 {#section_lkh_yk5_zdb .section}

J\_File\_PathToAllFileName\(文件夹路径\)

## 返回值 {#section_bcn_yk5_zdb .section}

返回文件夹下所有文件的集合。

## 样例 {#section_lpt_yk5_zdb .section}

```

Func Example46()
;获得文件夹下所有文件的集合
Local $file_all = J_File_PathToAllFileName("D:\pic\")
;查看集合文件的个数
Local $max = UBound($file_all)
;创建一个For循环，用来遍历全部文件
For $i = 1 To $max
;取出当前循环文件的名称
Local $file = J_EXP($file_all, "", $i)
;在当前“我的工具”视图中创建这条数据
J_CreateItem($file)
Next
EndFunc ;==>Example46
```

