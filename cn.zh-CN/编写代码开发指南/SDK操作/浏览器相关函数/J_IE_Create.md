# J\_IE\_Create {#concept_j45_dn5_zdb .concept}

创建一个IE窗口，返回一个窗口的对象。

## 函数 {#section_qgh_fn5_zdb .section}

J\_IE\_Create \(链接地址,\[尝试抓取:否\],\[是否等待:是\],\[浏览器类型\]\)

## 返回值 {#section_pg4_fn5_zdb .section}

返回浏览器对象，用于后续操作。

## 样例 {#section_bvt_fn5_zdb .section}

```

Func Example21()
;默认新建一个IE窗口并打开www.taobao.com链接,声明一个名为$ie的局域变量，装入这个新创建浏览器的对象
Local $ie = J_IE_Create("www.taobao.com")
;如果要用chrome打开
;Local $ie = J_IE_Create("www.taobao.com",default,default,default,'Chrome')
;左侧文件名 控件名 操作类型 内容 浏览器对象
;声明 $res1的一个局域变量，实现对于录制的控件进行输入文本“连衣裙”操作，并将执行的结果保存在这个变量中
Local $res1 = J_IE("淘宝网", "输入框", "输入", "连衣裙", $ie)
;判断操作是否成功，如果输入操作没成功，$res1的值为0，操作成功$res1的值就是1
If $res1 = 0 Then
;信息提示窗口显示提示信息给用户"连衣裙输入失败"
J_MsgBox("连衣裙输入失败")
;结束本次判断
EndIf
;声明 $res1的一个局域变量，实现对于录制的控件进行对控件“搜索”按钮进行点击操作，并将执行的结果保存在这个变量中
Local $res2 = J_IE("淘宝网", "搜索", "点击", "", $ie)
;判断操作是否成功，如果输入操作没成功，$res2的值为0，操作成功$res2的值就是1
If $res2 = 0 Then
;信息提示窗口显示提示信息给用户"搜索点击失败"
J_MsgBox("搜索点击失败")
;结束本次判断
EndIf
;声明 $text的一个局域变量，将$ie对应的浏览器对象获取页面所有可见文本，并将其保存至此变量中
Local $text = J_IE_Text($ie)
;信息提示窗口显示出变量$text中保存的全部文本
J_MsgBox($text)
EndFunc ;==>Example21
```

