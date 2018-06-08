# J\_INPUT {#concept_cb1_hmq_12b .concept}

弹出一个输入框接收用户输入的信息 。

## 函数 {#section_tfx_3mq_12b .section}

J\_INPUT\(标题,内容,\[类型：文本/密码\],\[宽度:默认200\],\[高度:默认125\]\)

## 返回值 {#section_l32_jmq_12b .section}

用户输入的内容。

## 样例 {#section_odk_jmq_12b .section}

```

Func Example45()
;声明一个局域变量，保存输入框返回的数据
Local $string = J_INPUT("请输入您的公司名称", "在这里输入您公司的名称", "文本", 200, 125)
EndFunc ;==>Example45
```

