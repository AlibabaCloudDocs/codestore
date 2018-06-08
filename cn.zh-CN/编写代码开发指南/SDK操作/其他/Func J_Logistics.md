# Func J\_Logistics {#concept_f21_rmq_12b .concept}

根据物流单号获取物流详情 。

## 函数 {#section_rs5_tmq_12b .section}

Func J\_Logistics\(“物流编号”, “物流服务商代码，可以不传”\)

## 返回值 {#section_vdb_5mq_12b .section}

物流详情的寄送对象。

## 样例 {#section_cfj_5mq_12b .section}

```

Func Example50()
;作用1:根据物流单号获取物流详情，返回物流详情的json格式
Local $sel = J_Logistics("310017000205")
;作用2:根据物流单号和服务商代码获取物流详情，返回物流详情的json格式，这比仅仅根据物流单号获取物流详情更准确
Local $sel = J_Logistics("310017000205","HTKY")
EndFunc ;==>Example50

ZTO
中通快递


YTO
圆通速递


STO
申通快递


YUNDA
韵达快递


HTKY
百世汇通


SF
顺丰速运


TTKDEX
天天快递


FAST
快捷快递


QFKD
全峰快递


GTO
国通快递


ZJS
宅急送


UC
优速物流


DBKD
德邦快递


EMS
EMS


EMS
中速快递


CNPOSTGJ
邮政国际包裹


POSTBBZ
邮政标准快递


POSTB
邮政快递包裹


DHLDE
DHL德国


KERRYEAS
嘉里大通


TMS56
加运美


POSTSE
瑞典邮政


TNT
TNT


UPS
UPS


USPS
USPS


DHLCN
DHL中国


ZTKY
中铁物流


ZTKY
飞豹快递


DHL
DHL全球


FEDEX
FedEx国际


FEDEXUS
FedEx美国


FEDEXCN
FedEx中国


POSTB
包裹信件


POSTTH
泰国邮政


XFWL
信丰物流


EWINSHINE
万象物流


RFD
如风达


ANE56
安能物流


HOAU
天地华宇


CNEX
佳吉快运


SURE
]]>
速尔快递


UAPEX
全一快递


QRT
全日通


ZENY
]]>
增益速递


GZFY
]]>
凡宇快递


XBWL
]]>
新邦物流


CAE
民航快递


CRE
中铁快运


FEC
银捷速递


FJSFWLJTYXGS
盛丰物流


HLWL
恒路物流


JDKD
京东快递


JIAYI
佳怡物流


KYE
跨越速运


LTS
联昊通


SZSA56
圣安物流


SHENGHUI
盛辉物流


SZKKE
京广速递


YCGWL
远成物流


YTZG
运通中港快递


POSTBR
巴西邮政


POSTCH
瑞士邮政


BLSYZ
比利时邮政


RBYZEMS
日本邮政


EPOST
韩国邮政


EYB
EMS经济快递


BESTQJT
百世物流


HUANGMAJIA
黄马甲配送


CHENGBANG
晟邦物流


GZLT
飞远配送


HZABC
飞远(爱彼西)配送


SNWL
苏宁快递


ZMKM
芝麻开门


JDYWL
筋斗云物流


BJCS
城市一百物流


LB
龙邦速递


YCT
黑猫宅急便


ROYALMAIL
英国皇家邮政


JKYZ
捷克邮政


BLYZ
波兰邮政


FGYZ
法国邮政


POSTTR
土耳其邮政


POSTCL
智利邮政


POSTBY
白俄罗斯邮政


POSTES
西班牙邮政


POSTUA
乌克兰邮政


POSTNO
挪威邮政


POSTZA
南非邮政


POSTPT
葡萄牙邮政


POSTSA
沙特邮政


POSTIN
印度邮政


POSTBG
保加利亚邮政


POSTAE
阿联酋邮政


POSTAU
澳大利亚邮政


POSTPK
巴基斯坦邮政


POSTMT
马耳他邮政


POSTLB
黎巴嫩邮政


POSTMD
摩尔多瓦邮政


POSTSRB
塞尔维亚邮政


POSTHR
克罗地亚邮政


POSTAM
亚美尼亚邮政


POSTMK
马其顿邮政


ONTRAC
OnTrac


CITYLINK
City-Link


COE
COE


DTW
大田物流


EES
百福东方


MBEX
民邦快递


HQKY
华企快运


YFEXPRESS
越丰物流


AIR
亚风速递


MANCOWL
万家物流


SZML56
明亮物流


CXCOD
传喜物流


4PX
递四方


POSTFI
芬兰邮政


POSTAR
阿根廷邮政


POSTSK
斯洛伐克邮政


SERPOST
秘鲁邮政


POSTIT
意大利邮政


POSTSI
斯洛文尼亚邮政


POSTHU
匈牙利邮政


POSTMU
毛里求斯邮政


POSTAT
奥地利邮政


POSTAL
阿尔巴尼亚邮政


POSTEE
爱沙尼亚邮政


ARAMEX
Aramex


SANTAI
三态速递


OCS
OCS


MYAAE
AAE全球专递


POSTLV
拉脱维亚邮政


YWWL
燕文物流


ASENDIA
Asendia USA


RUSTON
俄速通


XLOBO
贝海国际速递


SPSR
中俄快递


POSTCO
哥伦比亚邮政


SAD
赛澳递


SUIJIAWL
穗佳物流

```

