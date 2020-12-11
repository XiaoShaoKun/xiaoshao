---
description: 当 PBX 分机用户转移通话时，PBX 向应用服务器发送 “呼叫转移” 报告。
---

# ‘呼叫转移’报告



 注：

* 此转移只代表分机操作的转移，如：
  * 分机拨打特征码\*03，\*3将通话转接。
  * 分机设置呼叫转移功能。



### 报告参数

| 名称 | 类型 | 描述 |
| :--- | :--- | :--- |
| `action` | String | 呼叫转移事件。 |
| `callid` | String | 该通通话的 id。 |
| `ext` | String | 分机对象。 |
| `extid` | String | 发起转移的分机号。 |
| `inboundid` | String | 来电编码。 |
| `outboundid` | String | 去电编码。 |
| `outbound` | String | 对象参数。 |
| `inbound` | String | 对象参数。 |
| `from` | String | 来电的原始主叫号码。 |
| `to` | String | 来电的原始被叫号码。 |
| `trunk` | String | 通话过程中使用的中继名称。 |
| `sn` | String | PBX 的 SN 码。 |

### 报告示例

分机 101 与分机 102 通话中，分机 101 将电话转移到另外一个号码。

```text
POST  HTTP/1.1
Host:172.16.6.150
Content-Length:97
Accept: application/json
Content-Type:application/json
Connection:close

{
    "action":"Tranfer",
    "callid":"1589957670.2001",
    "ext":{
        "extid":[
            "102",
            "101"
        ]
    },
    "sn":"a09805021987"
}
```

外部用户 101 呼入PBX，与分机 102 通话，分机 102 将电话转移到另外一个号码。

```text
POST  HTTP/1.1
Host:172.16.6.150
Content-Length:176
Accept: application/json
Content-Type:application/json
Connection:close

{
    "action":"Tranfer",
    "callid":"1589957892.2030",
    "ext":{
        "extid":"102"
    },
    "inbound":{
        "from":"101",
        "to":"102",
        "trunk":"to-18-16-2",
        "inboundid":"1589957892.2030"
    },
    "sn":"a09805021987"
}
```

