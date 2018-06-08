# J\_IE\_Close {#concept_pky_5m5_zdb .concept}

可以通过IE窗体的对象、标题、地址、甚至是句柄关闭IE窗口。

## 函数 {#section_e13_ym5_zdb .section}

J\_IE\_Close \(窗口对象/窗口标题/窗口URL/窗口句柄\)

## 返回值 {#section_bzn_ym5_zdb .section}

-   0：失败
-   1：成功

## 样例 {#section_e2v_ym5_zdb .section}

```

Func Example23()
;新建一个IE窗口并打开www.taobao.com链接,声明一个名为$ie的局域变量，装入这个新创建浏览器的对象
Local $ie = J_IE_Create("www.taobao.com")
;通过变量$ie中保存的浏览器对象进行关闭浏览器操作
J_IE_Close($ie)
;新建一个IE窗口并打开ju.taobao.com链接,声明一个名为$ie的局域变量，装入这个新创建浏览器的对象
Local $ie = J_IE_Create("ju.taobao.com")
;通过浏览器窗口标题"聚划算"进行关闭浏览器操作
J_IE_Close("聚划算")
EndFunc ;==>Example23
```

