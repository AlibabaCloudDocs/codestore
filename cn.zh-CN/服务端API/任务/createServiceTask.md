createServiceTask 
======================================



调用地址：[https://api-rpa.aliyun.com/rpa/openapi/task/createServiceTask](#)调用方式：POST返回类型：JSON接口说明：创建服务型任务

**请求参数** 


|     名称      |   类型   | 是否必选 |                                                 示例值                                                 |                                                                                   描述                                                                                    |
|-------------|--------|------|-----------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| appId       | String | 是    | fb6a99a1-d8bd-46ee-8bed-2ed9cb5a0c0d                                                                | 应用唯一标识符                                                                                                                                                                 |
| appParams   | Json数组 | 否    | \[{"type":0,"name":"参数1","default":"","value":""},{"type":0,"name":"参数2","default":"","value":""}\] | 数字所代表的意思 TextEdit = 0,ComboBox = 1,  CheckedComboBox = 2, OpenFile = 3,OpenDir = 4,DateEdit = 5,ColorPick = 6,PasswordTextEdit = 7, HtmlTextEdit = 8, MultiTextEdit = 9 |
| clientId    | String | 否    | 5E77DA4EB87BCFB62A8B9527626A47F4                                                                    | 机器人唯一标识符                                                                                                                                                                |
| callbackUrl | String | 否    |                                                                                                     | 回调url                                                                                                                                                                   |





**返回参数** 

返回参数公共字段请查阅[返回结果](https://yuque.antfin-inc.com/cs-team-dev-cowork/rpa4/yxqiue)，返回参数中的 `data` 字段说明如下：


|    名称     |   类型   |                                       示例值                                        |    描述     |
|-----------|--------|----------------------------------------------------------------------------------|-----------|
| taskId    | String | fa2e5fb6-3461-4e90-8138-5797490eaa98                                             | task唯一标识符 |
| resultUrl | String | /rpa/openapi/task/queryServiceResult?taskId=fa2e5fb6-3461-4e90-8138-5797490eaa98 | 获取结果的url  |





**示例** 

请求示例：

    https://api-rpa.aliyun.com/rpa/openapi/task/createServiceTask?<公共请求参数>
    &appId=fb6a99a1-d8bd-46ee-8bed-2ed9cb5a0c0d
    &appParams=[{"type":0,"name":"参数一","default":"","value":""}]
    &clientId=5E77DA4EB87BCFB62A8B9527626A47F4
    &callbackUrl=http://api-rpa.aliyun.com/callback



返回示例：

    {
        "requestId":"e6cc72d4-cfa7-42f6-ba38-1aba346181e0",
        "success":true,
        "code":0,
        "msg":"调用成功",
        "msgCode":"result.success",
        "data":{
            "taskId":"fa2e5fb6-3461-4e90-8138-5797490eaa98",
            "resultUrl":"/rpa/openapi/task/queryServiceResult?taskId=fa2e5fb6-3461-4e90-8138-5797490eaa98"
        },
        "pager":null
    }



