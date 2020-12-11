---
description: 当 PBX 的分机拨打电话或收到来电时，PBX 会向第三方服务器发送回铃报告（ALERT）和响铃报告（RING）。
---

# ‘响铃&回铃’报告



 注：

* 必须在 PBX 的 API 配置界面启用分机的 状态监控，PBX 才会发送响铃报告和回铃报告。
* 同一个呼叫事件中，PBX 同时发送响铃报告和回铃报告。



### 报告参数-回铃事件

主叫拨打被叫号码后，被叫响铃后，主叫听到回铃音。

| 名称 | 类型 | 描述 |
| :--- | :--- | :--- |
| `action` | String | 回铃事件：ALERT。 |
| `callid` | String | 该通电话的 id。 |
| `call` | Object | 对象参数。 |
| 主叫为分机 |  |  |
| `ext` | Object | 分机对象。 |
| `extid` | String | 主叫号码。 |
| 主叫为外线号码 |  |  |
| `inbound` | Object | 外线来电对象。 |
| `from` | String | 主叫号码。 |
| `to` | String | 被叫号码。 |
| `trunk` | String | 通过哪条中继呼入。 |
| `inboundid` | String | 外线来电编号。 |
| `sn` | String | PBX 的 SN 码。 |

### 报告参数-响铃事件

被叫收到来电后，被叫听到响铃音。注： 响铃报告事件中会显示被叫号码和主叫号码。报告中，先显示被叫号码，再显示主叫号码。

| 名称 | 类型 | 描述 |
| :--- | :--- | :--- |
| `action` | String | 回铃事件：RING。 |
| `callid` | String | 该通电话的 id。 |
| `call` | Object | 对象参数。 |
| 主叫为分机，被叫为分机 |  |  |
| `ext` | Object | 分机对象。 |
| `extid` | String | 分机号码。 |
| 主叫为分机，被叫为外线号码，先显示`outbound`对象，再显示`ext`对象。 |  |  |
| `outbound` | Object | 外线去电对象。 |
| `from` | String | 主叫号码。 |
| `to` | String | 被叫号码。 |
| `trunk` | String | 通过哪条中继呼出。 |
| `outboundid` | String | 外线去电编码。 |
| 主叫为外线号码，被叫为分机，先显示`ext`对象，再显示`inbound`对象。 |  |  |
| `inbound` | Object | 外线来电对象。 |
| `from` | String | 主叫号码。 |
| `to` | String | 被叫号码。 |
| `trunk` | String | 通过哪条中继呼入。 |
| `inboundid` | String | 外线来电编号。 |
| `sn` | String | PBX 的 SN 码。 |

### 报告示例

分机 101呼叫分机 106。

```text
POST  HTTP/1.1
Host:172.16.6.150
Content-Length:89
Accept: application/json
Content-Type:application/json
Connection:close
{
    "action":"ALERT",
    "callid":"1589947952.1670",
    "ext":{
        "extid":[
            "101"
        ]
    },
    "sn":"a09805021987"
}

POST  HTTP/1.1
Host:172.16.6.150
Content-Length:94
Accept: application/json
Content-Type:application/json
Connection:close
{
    "action":"RING",
    "callid":"1589947952.1670",
    "ext":{
        "extid":["106","101"]
    },
    "sn":"a09805021987"
}
```

分机106 拨打外线号码 16103。

```text
POST  HTTP/1.1
Host:172.16.6.150
Content-Length:67
Accept: application/json
Content-Type:application/json
Connection:close

{
    "action":"ALERT",
    "callid":"1589948179.1692",
    "ext":{
        "extid":"106"
    }
}

POST  HTTP/1.1
Host:172.16.6.150
Content-Length:155
Accept: application/json
Content-Type:application/json
Connection:close

{
    "action":"RING",
    "callid":"1589948178.1690",
    "outbound":{
        "from":"106",
        "to":"103",
        "trunk":"to-18-16-2",
        "outboundid":"1589948178.1690"
    },
    "ext":{
        "extid":"106"
    }
}
```

外线号码103呼叫分机101。

```text
POST  HTTP/1.1
Host:172.16.6.150
Content-Length:152
Accept: application/json
Content-Type:application/json
Connection:close

{
    "action":"ALERT",
    "callid":"1589948512.1709",
    "inbound":{
        "from":"103",
        "to":"101",
        "trunk":"to-18-16-2",
        "inboundid":"1589948512.1707"
    },
    "sn":"a09805021987"
}

POST  HTTP/1.1
Host:172.16.6.150
Content-Length:173
Accept: application/json
Content-Type:application/json
Connection:close

{
    "action":"RING",
    "callid":"1589948512.1709",
    "ext":{
        "extid":"101"
    },
    "inbound":{
        "from":"103",
        "to":"101",
        "trunk":"to-18-16-2",
        "inboundid":"1589948512.1707"
    },
    "sn":"a09805021987"
}
```

