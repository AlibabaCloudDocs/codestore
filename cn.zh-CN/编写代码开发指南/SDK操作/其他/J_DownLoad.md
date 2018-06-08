# J\_DownLoad {#concept_chn_clq_12b .concept}

从URL地址下文件至本机，如路径为空，则返回html代码。

## 函数 {#section_zp4_2lq_12b .section}

J\_DownLoad\(URL地址,保存本机的路径,\[编码:1\]\)

## 编码 {#section_ntv_2lq_12b .section}

默认1，仅在保存本机路径为空的时候生效，编码为0的时候返回二进制编码。

## 返回值 {#section_ldc_flq_12b .section}

无。

## 样例 {#section_zvq_3lq_12b .section}

```

Func Example36()
Local $url = "https://img.alicdn.com/bao/uploaded/i2/TB1nuG0GXXXXXa2aXXXXXXXXXXX_!!0-item_pic.jpg_130x130.jpg"
;将url地址的图片下载并保存至本地D:\1.jpg
J_DownLoad($url, "D:\1.jpg")
EndFunc ;==>Example36
```

