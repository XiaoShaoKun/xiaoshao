---
description: 通过本接口可将指定分机的当前通话保持。如需恢复通话，可使用通话接回接口。
---

# 通话保持



### Endpoint

```text
POST /api/v0.0.1/extension/hold?token={token}&type={type}
```

### 请求参数

| 名称 | 是否必需 | 类型 | 描述 |
| :--- | :--- | :--- | :--- |
| `extid` | 是 | Int | 保持该分机的当前通话。 |

### 实际示例

**请求示例**

```text
POST /api/v0.0.1/extension/hold?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
    "extid": "101"
}
```

```text
POST /api/v0.0.1/extension/hold?token=813b621cfe8eecf445a2ce1f4a079ffe&type=xml HTTP/1.1
Content-Type:application/xml; charset=utf-8
Host: 172.16.6.150
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
	<extid>101</extid>
</xml>

	

```

**响应示例**

```text
HTTP/1.1 200 OK
Access-control-allow-origin: *
Access-control-allow-methods: GET, POST, OPTIONS, PUT, DELETE
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
	<extid>101</extid>
</xml>
```

