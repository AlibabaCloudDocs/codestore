# J\_Rest\_Get {#concept_jf3_qnq_12b .concept}

rest接口get方法。

## 函数 {#section_yjp_snq_12b .section}

J\_Rest\_Get\($url,$header=’’,浏览器对象=’’\)

若指定浏览器对象，调用rest接口时会加上该浏览器的session。

其中$header,键值对，多个值以换行符连接。

## 返回值 {#section_r3w_snq_12b .section}

成功返回调用结果，失败返回0。

## 样例 {#section_xgv_tnq_12b .section}

```

func test()
local $url = "http://api.daily.taobao.net/router/rest?sign=45E8A4332BEC46289386F25954DB2706&timestamp=2016-10-28+19%3A34%3A49&v=2.0&app_key=4272&method=taobao.juwuba.user.getrsa&partner_id=top-apitools&format=json"
local $result = J_Rest_Get($url)
if $result=0 then
local $msg = J_GetErrorMsg()
j_msgbox($msg)
endif
j_log($result)
endfunc ;==>test
func test1()
local $ie = J_IE_Catch("码栈", "标题", "chrome")
local $url = "http://codestore.daily.taobao.net/services/cs/task/sdks/744/depend"
local $result = J_Rest_Get($url, '', $ie)
if $result = 0 then
local $msg = J_GetErrorMsg()
j_msgbox($msg)
endif
j_log($result)
EndFunc ;==>test1
```

