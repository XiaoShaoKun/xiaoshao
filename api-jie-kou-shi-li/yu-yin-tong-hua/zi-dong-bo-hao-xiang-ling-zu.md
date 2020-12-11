---
description: PBX 会自动拨打外线号码，当外线被接听后，PBX 会将这通电话转接到指定的响铃组。
---

# 自动拨号（响铃组）



### Endpoint

```text
POST /api/v0.0.1/ringgroup/dial_outbound?token={token}&type={type}
```

### 请求参数

| 名称 | 是否必需 | 类型 | 描述 |
| :--- | :--- | :--- | :--- |
| `ringgroupid` | 是 | Int | 响铃组号码。 |
| `outto` | 是 | String | 要拨打的外线号码。 |

### 响应参数

| 名称 | 类型 | 描述 |
| :--- | :--- | :--- |


### 实际示例

**请求示例**

```text
POST /api/v0.0.1/ringgroup/dial_outbound?token=813b621cfe8eecf445a2ce1f4a079ffe*type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 192.168.5.150
{
    "ringgroupid": "600",
    "outto": "16103"
}
```

```text
POST /api/v0.0.1/ringgroup/dial_outbound?token=813b621cfe8eecf445a2ce1f4a079ffe&type=xml HTTP/1.1
Content-Type:application/xml; charset=utf-8
Host: 192.168.5.150
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
	<ringgroupid>600</ringgroupid>
	<outto>16103</outto>
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

