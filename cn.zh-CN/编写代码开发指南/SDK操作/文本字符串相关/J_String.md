# J\_String {#concept_xsy_gf4_12b .concept}

对字符串操作函数的汇总 。

## 函数 {#section_iwf_3f4_12b .section}

J\_String\(总字符串，操作行为，参数值\)

## 操作行为 {#section_m2l_3f4_12b .section}

是否包含长度、取左子串、取右子串、取子串、转小写、转大写、仅数字、仅字母、仅小写、仅大写和拆分。

## 样例 {#section_vnq_3f4_12b .section}

```

Func StringDemo()
;1、判断字符串中有无包含某个子串,如果包含，返回子串包含的位置，否则返回0
local $str1 = "我是一个字符串"
if J_String($str1,'是否包含','字符') > 0 then
J_MsgBox('包含子串')
endif
;2、取字符串长度
local $len = J_String($str1,'长度')
J_MsgBox("长度:"&$len)
;3、从左边取子串:从左边第一个字符开始，参数值为要取的字符串长度
local $subStr1 = J_String($str1,'取左子串','2')
J_MsgBox($subStr1);我是
;4、从右边取子串：从最后一个字符开始，参数值为要取的字符串长度
local $subStr2 = J_String($str1,'取右子串','3')
J_MsgBox($subStr2);
;5、取子串:参数值需要有提供2个数据，以英文逗号割开：开始位置,截取子串长度
;将其中的“一个”提取出来,从第3个字符开始取，取2个字符
local $subStr3 = J_String($str1,'取子串','3,2')
J_MsgBox($subStr3)
;6、转化
local $str2 = "Hello"
;转成小写
local $subStr4 = J_String($str2,'转小写','')
J_MsgBox($subStr4);hello
;转成大写
local $subStr5 = J_String($str2,'转大写','')
J_MsgBox($subStr5);HELLO
;7、判断
;是否纯数字
local $str3="1234"
if J_String($str3,'仅数字','') = 1 then 
J_MsgBox('字符串是纯数字')
endif
;是否纯平字母a到z,A到Z
local $str4="abcADK"
if J_String($str4,'仅字母') = 1 then 
J_MsgBox('字符串是纯字母')
endif
;字母串中是否仅包括：小写字母 a到z
local $str6='abcd'
if J_String($str6,'仅小写') = 1 then 
J_MsgBox('字符串中全是小写字母')
endif
;字母串中是否仅包括：大写字母 A到Z
local $str6='CDFEF'
if J_String($str6,'仅大写') = 1 then 
J_MsgBox('字符串中全是大写字母')
endif
;8、拆分：返回值是数组，数组第一个元素值为子串的数量
local $str7 = "123,456,788"
local $array = J_String($str7,'拆分',',')
;拆分成几个串了
local $len = $array[0]
;其它元素
for $i = 1 to UBound($array) -1
J_LOG('元素：'&$array[$i])
next
EndFunc ;==>
```

