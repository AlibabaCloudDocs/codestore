# J\_Word\_CursorMove {#concept_w4f_43q_12b .concept}

移动Word文档中的光标，移动方向：上/下/左/右 。

## 函数 {#section_tf4_q3q_12b .section}

J\_Word\_CursorMove\(Word对象, 移动步数,\[移动方向:右\]\)

## 返回值 {#section_sfz_q3q_12b .section}

成功返回1，失败返回0。

## 样例 {#section_trf_r3q_12b .section}

```

Func Example39()
;前台创建一个word文档，可见
Local $doc1 = J_Word_Create("是")
;前台打开D:\1.docx word文档，可见
Local $doc2 = J_Word_Open("D:\1.docx", "是")
;光标向下移动4行
J_Word_CursorMove($doc2, 4, "下")
;光标向右移动3个字符
J_Word_CursorMove($doc2, 3, "右")
;插入文本 你好啊~，字号12，宋体，颜色位置是3，加粗
J_Word_Write($doc2, "你好啊~", 12, "宋体", 3, "是")
;从当前位置向后查找第二个"你好啊2"文本，并把光标放在你好啊2前面
J_Word_SeatchText($doc2, "你好啊2", "当前", 2, "前")
;插入文本，“在这里”，字号12，字体微软雅黑，颜色位置1，不加粗
J_Word_Write($doc2, "在这里", 12, "微软雅黑", 1, "否")
;保存doc2
J_Word_Save($doc2)
;读取doc2全部文本内容
Local $allstring = J_Word_Read($doc2)
;把读取的内容写入到doc1里面
J_Word_Write($doc1, $allstring)
;将doc1文档保存为D:\newdoc.docx
J_Word_Save($doc1, "D:\newdoc.docx")
;关闭文档1
J_Word_Close($doc1)
;关闭文档2
J_Word_Close($doc2)
;结束word操作
J_Word_Quit()
;将D:\newdoc.docx转换成D:\1.pdf，注意此函数非word操作，而是文件格式的转变
J_WordToPDF("D:\newdoc.docx", "D:\1.pdf")
EndFunc ;==>Example39
```

