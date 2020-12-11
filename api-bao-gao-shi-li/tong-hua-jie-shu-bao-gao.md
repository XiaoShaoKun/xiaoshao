---
description: >-
  当一路通话释放，即通话挂断时，PBX 会向第三方应用服务器发送两个 BYE 报告。在第一个
  BYE报告中，先记录主动挂断电话的用户号码，后记录被挂断电话的用户号码。
---

# ‘通话结束’报告



### 报告参数

| 名称 | 类型 | 描述 |
| :--- | :--- | :--- |
| `action` | String | 通话结束报告。 |
| `callid` | String | 该通通话的 id。 |
| `ext` | String | 分机对象。 |
| `extid` | String | 分机号。 |
| `inboundid` | String | 来电编码。 |
| `outboundid` | String | 去电编码。 |
| `outbound` | String | 对象参数。 |
| `inbound` | String | 对象参数。 |
| `from` | String | 来电的原始主叫号码。 |
| `to` | String | 来电的原始被叫号码。 |
| `trunk` | String | 通过哪条中继呼入。 |
| `sn` | String | PBX 的 SN 码。 |

### 报告示例

分机101与分机106通话中，分机 106挂断电话。

```text
POST  HTTP/1.1
Host:172.16.6.150
Content-Length:93
Accept: application/json
Content-Type:application/json
Connection:close

{
    "action":"BYE",
    "callid":"1589953914.1775",
    "ext":{
        "extid":[
            "106",
            "101"
        ]
    },
    "sn":"a09805021987"
}

POST  HTTP/1.1
Host:172.16.6.150
Content-Length:93
Accept: application/json
Content-Type:application/json
Connection:close

{
    "action":"BYE",
    "callid":"1589953914.1777",
    "ext":{
        "extid":[
            "101",
            "106"
        ]
    },
    "sn":"a09805021987"
}
```

分机 106 与外部用户 103 通话中，外部用户 103 挂断电话。

```text
POST  HTTP/1.1
Host:172.16.6.150
Content-Length:174
Accept: application/json
Content-Type:application/json
Connection:close

{
    "action":"BYE",
    "callid":"1589956488.1962",
    "outbound":{
        "from":"106",
        "to":"103",
        "trunk":"to-18-16-2",
        "outboundid":"1589956488.1962"
    },
    "ext":{
        "extid":"106"
    },
    "sn":"a09805021987"
}

POST  HTTP/1.1
Host:172.16.6.150
Content-Length:174
Accept: application/json
Content-Type:application/json
Connection:close

{
    "action":"BYE",
    "callid":"1589956489.1964",
    "ext":{
        "extid":"106"
    },
    "outbound":{
        "from":"106",
        "to":"103",
        "trunk":"to-18-16-2",
        "outboundid":"1589956489.1964"
    },
    "sn":"a09805021987"
}
```

