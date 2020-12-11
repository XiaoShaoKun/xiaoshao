---
description: 通过本接口可以指定挂断外线呼入到 PBX 系统的通话。
---

# 挂断来电（强拆）



### Endpoint

```text
POST /api/v0.0.1/inbound/hangup?token={token}&type={type}
```

### 请求参数

| 名称 | 是否必需 | 类型 | 描述 |
| :--- | :--- | :--- | :--- |
| `inboundid` | 是 | String | 外线来电编号。 |

### 实际示例

**请求示例**

```text
POST /api/v0.0.1/inbound/hangup?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
	"inboundid":"1589938168.1111"
}
```

```text
POST /api/v0.0.1/inbound/hangup?token=813b621cfe8eecf445a2ce1f4a079ffe&type=xml HTTP/1.1
Content-Type:application/xml; charset=utf-8
Host: 172.16.6.150
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
	<inboundid>1589938168.1111</inboundid>
</xml>
```

**响应示例**

```text
HTTP/1.1 200 OK
Access-control-allow-origin: *
Access-control-allow-methods: GET, POST, OPTIONS, PUT, DELETE
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
	<status>Success</status>
</xml>
```

