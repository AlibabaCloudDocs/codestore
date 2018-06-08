# J\_ShortMsg {#concept_os1_t4q_12b .concept}

根据阿里大鱼的模板发送短信。

## 函数 {#section_dp4_v4q_12b .section}

J\_ShortMsg\(“阿里大鱼应用key”, “阿里大鱼应用秘钥”, “阿里大鱼的短信模板id”, “手机号”, “阿里大鱼的短信签名” , “短信模板中的参数，如果没有可以为空”\)

## 返回值 {#section_dmx_v4q_12b .section}

是否发送成功。

-   0表示失败。

-   1表示成功。


## 使用方法 {#section_eyw_w4q_12b .section}

1.  阿里大鱼申请阿里大鱼的账户，地址为[阿里大鱼账号](http://www.alidayu.com/)。

2.  按照阿里云的指引开通云通信服务。

3.  创建阿里云的AccessKey 和Access Secret，地址为[AK创建地址](https://ak-console.aliyun.com/?spm=5176.sms-account.101.257.66e3621ByUmVb#/accesskey)

4.  设置短信模板，模板需要申请，审核通过后就可以使用，地址为[审核地址](https://dysms.console.aliyun.com/dysms.htm?spm=a3142.8039393.0.0.3cdd782f4A9p71#/sign)。

5.  单击**详情**，可以查看模板详情。

6.  设置短信签名和短信模板一样，申请地址为[申请地址](https://dysms.console.aliyun.com/dysms.htm?spm=a3142.8039393.0.0.3cdd782f4A9p71#/sign)。


## 样例 {#section_vzp_bpq_12b .section}

```

Func Example51()
;作用1:发送短信 $msgParams 是模板中的变量，用JSON 格式的方式传入
Local $msgParams = '{"code":"122456","product":"阿里码栈"}' ;
J_ShortMsg("23330602","765xxxxxxxxxxxxxxxx40","SMS_5012690","13312341234",,"活动验证" $msgParams )
EndFunc ;==>Example51
```

