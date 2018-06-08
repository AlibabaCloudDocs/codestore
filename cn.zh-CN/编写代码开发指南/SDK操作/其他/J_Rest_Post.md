# J\_Rest\_Post {#concept_xgl_ynq_12b .concept}

rest接口post方法。

## 函数 {#section_yf4_14q_12b .section}

J\_Rest\_Post\($url,$header=’’,$data=’’,浏览器对象=’’\)

若指定浏览器对象，调用rest接口时会加上该浏览器的session。

其中$header/Data为键值对，多个值以换行符连接。

## 返回值 {#section_bp5_14q_12b .section}

成功返回调用结果，失败返回0。

## 样例 {#section_yk1_b4q_12b .section}

```

func test()
;调用登录接口，获取session
local $url = "http://codestore.daily.taobao.net/services/cs/user/login/buclogin"
local $data = "userName=XXXX" & @CRLF
$data &= "password=YYYY" & @CRLF
$data &= "ip=127.0.0.1" & @CRLF
$data &= "publicKey=XX" & @CRLF
$data &= "versionNumber=XXX" & @CRLF
local $result = J_Rest_Post($url, '', $data)
if $result = 0 then
local $msg = J_GetErrorMsg()
j_msgbox($msg)
endif
;调用请求接口
local $url2 = "http://codestore.daily.taobao.net/services/cs/task/sdks/744/depend"
local $result2 = J_Rest_Get($url2, '', '')
j_log($result2)
EndFunc ;==>test3
```

