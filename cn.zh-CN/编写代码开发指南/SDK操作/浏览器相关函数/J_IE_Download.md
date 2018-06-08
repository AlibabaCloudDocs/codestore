# J\_IE\_Download {#concept_ap2_jn5_zdb .concept}

模拟浏览器中点击下载保存动作，将文件保存到指定的地方。文件名可以特别指定，指定时，要注意文件类型。

## 函数 {#section_m5q_kn5_zdb .section}

J\_IE\_Download\($url, $path, $fileName = ‘’\)

## 返回值 {#section_rhy_kn5_zdb .section}

-   0：失败
-   1：成功

**说明：** 异步下载，不等待文件下载完就返回结果。

## 样例 {#section_tnf_ln5_zdb .section}

```

func downloadTest()
;需先登录商家后台
Local $url = "https://trade.taobao.com/trade/itemlist/export_by_tfs.do?f_p=TB1EfhDOpXXXXXQXVXXUXJ7WFXX-a9722f6c478344a5124fb76750a88441-orders&apply_time=2016-11-18+14%3A08%3A51&start_time=2016-08-20+14%3A08%3A51&end_time=2016-11-18+14%3A08%3A51&order_status=%BD%BB%D2%D7%B9%D8%B1%D5"
local $result = J_IE_Download($url, 'd:/nw/')
if $result = 0 then
local $msg = J_GetErrorMsg()
J_MsgBox($msg)
endif
EndFunc ;==>downloadTest
```

