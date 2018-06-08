# J\_View\_Show {#concept_d1w_1y4_12b .concept}

让数据列表中的某行数据显示出来。

## 函数 {#section_drk_cy4_12b .section}

J\_View\_Show \(行号\)

## 返回值 {#section_nlv_cy4_12b .section}

1：返回成功。

## 样例 {#section_s2c_dy4_12b .section}

```

Func Example()
;声明 $index的一个局域变量，将当前“我的应用”中数据列表中第20行数据置为可见状态，并将结果保存在这个变量中（结果一定是1）
Local $index = J_View_Show(20)
EndFunc ;==>Example
```

