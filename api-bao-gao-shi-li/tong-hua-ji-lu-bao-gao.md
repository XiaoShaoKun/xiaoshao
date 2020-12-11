---
description: 当通话结束后，PBX 向应用服务器实时发送通话详细记录（CDR）。
---

# ‘通话记录’报告



### 报告参数

| 名称 | 类型 | 描述 |
| :--- | :--- | :--- |
| `action` | String | 通话事件。 |
| `timestart` | String | 开始时间。 |
| `callfrom` | String | 主叫号码。 |
| `callto` | String | 被叫号码。 |
| `callduraction` | String | 通话时长。 |
| `talkduraction` | String | 接听时长。 |
| `status` | String | 通话状态。 |
| `type` | String | 通话类型。 |
| `recording` | String | 全局录音文件名。 |
| `sn` | String | PBX 的 SN 码。 |

### 报告示例

分机 106 呼叫分机 102。

```text
POST  HTTP/1.1
Host:172.16.6.150
Content-Length:211
Accept: application/json
Content-Type:application/json
Connection:close

{
    "action":"NewCdr",
    "callid":"1589958682.2101",
    "timestart":"2020-05-20 10:11:22",
    "callfrom":"106",
    "callto":"102",
    "callduraction":"10",
    "talkduraction":"5",
    "status":"ANSWERED",
    "type":"Internal",
    "sn":"a09805021987"
}
```

分机 106 呼叫外部号码 101。

```text
POST  HTTP/1.1
Host:172.16.6.150
Content-Length:213
Accept: application/json
Content-Type:application/json
Connection:close

{
    "action":"NewCdr",
    "callid":"1589958787.2118",
    "timestart":"2020-05-20 10:13:07",
    "callfrom":"106",
    "callto":"16101",
    "callduraction":"10",
    "talkduraction":"5",
    "status":"ANSWERED",
    "type":"Outbound",
    "sn":"a09805021987"
}
```

外部用户 101 呼入分机 102。

```text
POST  HTTP/1.1
Host:172.16.6.150
Content-Length:210
Accept: application/json
Content-Type:application/json
Connection:close

{
    "action":"NewCdr",
    "callid":"1589959139.2135",
    "timestart":"2020-05-20 10:18:59",
    "callfrom":"101",
    "callto":"102",
    "callduraction":"10",
    "talkduraction":"4",
    "status":"ANSWERED",
    "type":"Inbound",
    "sn":"a09805021987"
}

```

