---
description: 当 PBX 的分机正在通话时，可使用该接口将通话转移到其他号码，如分机、队列、响铃组、IVR、或外线号码。
---

# 通话转接



### Endpoint

```text
POST /api/v0.0.1/calltransfer?token={token}&type={type}
```

### 请求参数

| 参数 | 是否必需 | 类型 | 描述 |
| :--- | :--- | :--- | :--- |
| `callid` | 是 | String | 外线来电编号。 |
| `transferor` | 是 | String | 指定由通话中的哪一方发起转移，发起转移后，转移方将自动挂断电话。 |
| `transferto` | 是 | String | 转移到哪个号码。 |

### 实际示例

**请求示例**

```text
POST /api/v0.0.1/calltransfer?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
	"callid": "1589940297.1207",
	"transferor":"101",
	"transferto":"16103"
}
```



```text
POST /api/v0.0.1/calltransfer?token=813b621cfe8eecf445a2ce1f4a079ffe&type=xml HTTP/1.1
Content-Type:application/xml; charset=utf-8
Host: 172.16.6.150
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
	<callid>1589940297.1207</callid>
	<transferor>101</transferor>
	<transferto>16103</transferto>
</xml>
```

**响应示例**

```text
HTTP/1.1 200 OK
Access-control-allow-origin: *
Access-control-allow-methods: GET, POST, OPTIONS, PUT, DELETE
{
    "status": "Success"
}
```

```text
HTTP/1.1 200 OK
Access-control-allow-origin: *
Access-control-allow-methods: GET, POST, OPTIONS, PUT, DELETE
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
	<status>Success</status>
</xml>
```

