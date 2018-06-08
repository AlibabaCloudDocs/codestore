# J\_Email {#concept_trd_llq_12b .concept}

模拟邮箱发邮件。

## 函数 {#section_hdf_nlq_12b .section}

J\_Email\(smtp服务器,邮件发送人,邮件发送者地址,邮件发送给谁,邮件标题,邮件正文,附件地址,CC,BCC,用户名,密码,\[发送端口=465\],\[ssl=993\]\)

## 返回值 {#section_b2m_nlq_12b .section}

成功返回1，失败返回0。

## 样例 {#section_lms_nlq_12b .section}

```

Func Example44()
;声明一个局域变量，保存邮件发送的结果
Local $res = J_Email("smtp.taobao.com", "镖头", "biaotou@taobao.com", "gulie@taobao.com", "邮件通知测试", "邮件正文支持html代码", "D:1/jpg;D:\2.jpg", "", "", "username", "password")
If $res = 1 Then
J_MsgBox("发送成功")
Else
J_MsgBox("发送失败")
EndIf
EndFunc ;==>Example44
```

