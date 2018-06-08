# J\_View\_MaxCount {#concept_vs2_dx4_12b .concept}

查看数据列表中一共有多少条数据，一般情况下用于循环。

## 函数 {#section_j5t_jx4_12b .section}

J\_View\_MaxCount \(\)

## 返回值 {#section_d3d_kx4_12b .section}

返回码栈视图中一共多少行（数字）。

## 样例 {#section_sz3_kx4_12b .section}

```

Func Example17()
;声明 $result1的一个局域变量，并将当前“我的应用”中数据列表中全部数据的条数保存在这个变量中
Local $max = J_View_MaxCount()
;意图把视图中的数据从第一条开始全部遍历一遍
;从1循环到$max中保存的总数据条数，步长为1，即1,2,3,4...
For $i = 1 To $max Step 1
;信息提示窗，显示变量 $i的数据
J_MsgBox($i)
;下一次循环
Next
EndFunc ;==>Example17
```

