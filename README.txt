数据连接器json的整体格式如下：
###代码块开始
[
    //组件1
    {},
    //组件2
    {}
]
###代码块结束
其中每个组件的格式如下：
定时任务格式如下：
###代码块开始
{
    "tagName": "scheduler",
    "properties": {
        "doc:id": "64bbb3db-8a1d-4982-8863-6213faf7f726", // 32位的随机id
        "_edition": "3.0.0", //版本
        "_orderId": "1",// 组件的位置
        "_nodeRemark": "", // 组件的备注
        "_operation": "create-scheduler", 
        "mode": "2", // 2: 图形化配置，1: cron配置
        "location": "Asia/Chongqing", // 时区
        "cron": "",
        "once_trigger_list": ""
    },
    "children": [
        {
            "tagName": "periodic_trigger_rule",
            "properties": {
                "interval": "5", 
                "unit": "minutes",
                "months": "",
                "week": "",
                "days": "",
                "hours": "",
                "minutes": "",
                "seconds": "0"
            }
        }
    ]
}
###代码块结束
HTTP请求格式如下：
###代码块开始
{
    "tagName": "http:request",
    "properties": {
        "doc:id": "713da06a-e878-43c9-891e-b8ce75ce97aa",
        "_edition": "3.0.0",
        "_orderId": "2", // 组件位置
        "_nodeRemark": "",
        "_operation": "send-request",
        "connection-ref": "10251",
        "config-ref": "10251",
        "_checkFormErrorStatus": "",
        "method": "GET", // 请求方式
        "DataConsumptionStrategy": "repeatable",
        "urlOrPath": "$[{\"type\":\"string\",\"mode\":\"template\",\"pieces\":[{\"mode\":\"value\",\"type\":\"string\",\"value\":\"http://www.qq.com\"}]}]"
    }, // 表达式格式
    "children": [
        {
            // 请求参数
            "tagName": "http:query-params",
            "properties": {},
            "children": [
                {
                    "tagName": "value",
                    "properties": {
                        "type": "dict",
                        "custom_type_name": "dict"
                    },
                    "children": [
                        {
                            "tagName": "item",
                            "idx": "1",
                            "properties": {},
                            "children": [
                                {
                                    "tagName": "key",
                                    "properties": {
                                        "type": "string",
                                        "value": "name"
                                    }
                                },
                                {
                                    "tagName": "value",
                                    "properties": {
                                        "type": "string",
                                        "custom_type_name": "string",
                                        "value": "luhao"
                                    },
                                    "children": []
                                }
                            ]
                        }
                    ]
                }
            ],
            "value": ""
        },
        {
            // 请求头
            "tagName": "http:headers",
            "properties": {},
            "children": [
                {
                    "tagName": "value",
                    "properties": {
                        "type": "dict",
                        "custom_type_name": "dict"
                    },
                    "children": [
                        {
                            "tagName": "item",
                            "idx": "1",
                            "properties": {},
                            "children": [
                                {
                                    "tagName": "key",
                                    "properties": {
                                        "type": "string",
                                        "value": "Content-Type"
                                    }
                                },
                                {
                                    "tagName": "value",
                                    "properties": {
                                        "type": "string",
                                        "custom_type_name": "string",
                                        "value": "application/json"
                                    },
                                    "children": []
                                }
                            ]
                        }
                    ]
                }
            ],
            "value": ""
        }
    ]
}
###代码块结束
