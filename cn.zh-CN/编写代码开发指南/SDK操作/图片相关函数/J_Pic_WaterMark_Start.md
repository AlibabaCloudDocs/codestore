# J\_Pic\_WaterMark\_Start {#concept_iwg_dzn_12b .concept}

开启目标图片作为打水印的主图，必须先使用此函数。

## 函数 {#section_dtv_2zn_12b .section}

J\_Pic\_WaterMark\_Start\(原始图片地址,保存图片地址\)

## 返回值 {#section_wvb_fzn_12b .section}

无。

## 样例 {#section_swg_fzn_12b .section}

```

Func Example40()
;截取屏幕起始坐标1,1 结束坐标为500,800 的屏幕矩形区域，并保存文件为D:\1.jpg
J_Pic_Capture("D:\1.jpg", 1, 1, 500, 800)
;开始图片处理，初始文件是"D:\1.jpg"，处理之后打算把文件另存为"D:\2.jpg"
J_Pic_WaterMark_Start("D:\1.jpg", "D:\2.jpg")
;在被处理图片的100,50 像素处打上logo水印（水印路径：D:\logo.png）
J_Pic_WaterMark_Logo("D:\logo.png", 100, 50)
;在被处理图片的400,400 像素处打上文本水印，文本字体为红色，字体微软雅黑，字号12号，带下划线的
J_Pic_WaterMark_Text("taobao.com", 400, 400, 0xFFFF0000, "微软雅黑", 12, "下划线")
;在被处理图片的450,450像素处打上文本水印，字型字号等都是默认的
J_Pic_WaterMark_Text("copy right", 450, 450)
;结束打水印操作，设置保存的图片清晰度为50%
J_Pic_WaterMark_End(50)
;等比例设置图片D:\2.jpg高度为1000，并另存为D:\3.jpg
J_Pic_Resize("D:\2.jpg", "D:\3.jpg", 1000, "高度")
;等比例设置图片D:\2.jpg宽度为2000，并另存为D:\4.jpg
J_Pic_Resize("D:\2.jpg", "D:\4.jpg", 2000, "宽度")
;设置图片D:\2.jpg宽度为700高度为1000，并另存为D:\5.jpg
J_Pic_Resize("D:\2.jpg", "D:\5.jpg", 700, 1000)
EndFunc ;==>Example40
```

