# J\_IE\_Back {#concept_uwp_fm5_zdb .concept}

浏览器执行后退动作。

## 函数 {#section_bjg_hm5_zdb .section}

J\_IE\_Back\(浏览器对象\)

## 返回值 {#section_zpn_hm5_zdb .section}

-   0：失败
-   1：成功

## 样例 {#section_f1v_hm5_zdb .section}

```

Func Example43()
;声明一个居于变量，保存通过链接地址定位的浏览器对象
Local $ie = J_IE_Catch("taobao.com", "地址")
;在浏览器中实现点击女装类目操作
J_IE("淘宝网", "女装类目", "点击", "", $ie)
;页面刷新后实现，浏览器后退功能
J_IE_Back($ie)
EndFunc ;==>Example43
```

