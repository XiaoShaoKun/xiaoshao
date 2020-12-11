---
description: 通过本接口可以指定挂断当前 IPPBX 系统分机通过外线呼出的通话。
---

# 挂断去电（强拆）



### Endpoint

```text
POST /api/v0.0.1/outbound/hangup?token={token}&type={type}
```

### 请求参数

| 名称 | 是否必需 | 类型 | 描述 |
| :--- | :--- | :--- | :--- |
| `outboundid` | 是 | String | 外线去电编号。 |

### 实际示例

**请求示例**

```text
POST /api/v0.0.1/outbound/hangup?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
    "outboundid":"1589938378.1130"
}
```

```text
POST /api/v0.0.1/outbound/hangup?token=813b621cfe8eecf445a2ce1f4a079ffe&type=xml HTTP/1.1
Content-Type:application/xml; charset=utf-8
Host: 172.16.6.150
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
	<outboundid>1589938378.1130</outboundid>
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

