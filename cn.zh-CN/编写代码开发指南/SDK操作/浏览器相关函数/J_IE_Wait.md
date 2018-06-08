# J\_IE\_Wait {#concept_upt_pyn_12b .concept}

等待录制的控件刷新。

## 函数 {#section_rvg_ryn_12b .section}

J\_IE\_Wait\(浏览器对象,MAP名称,控件名称,\[超时时间:10000毫秒\]\)

## 返回值 {#section_ozl_ryn_12b .section}

-   1：成功
-   0：失败

## 样例 {#section_g4r_ryn_12b .section}

```

Func Example29()
;新建一个IE窗口并打开www.crm.admin.com链接,声明一个名为$ie的局域变量，装入这个新创建浏览器的对象
Local $ie = J_IE_Create("www.baidu.com")
;声明 $res1的一个局域变量，$ie对应的浏览器页面等待录制控件工具中相对应的控件在20000毫秒内出现，并将等待结果保存至变量中（成功1，失败0）
Local $result = J_IE_Wait($ie, "淘宝网", "搜索框exp", 20000)
;等待结束并将等待的结果通过信息提示窗口的形式显示出来
J_MsgBox("等待结束：" & $result)
EndFunc ;==>Example29
```

