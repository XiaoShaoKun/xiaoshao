---
description: 通过本接口可将分机保持的通话重新恢复。
---

# 恢复通话



### Endpoint

```text
POST /api/v0.0.1/extension/unhold?token={token}&type={type}
```

### 请求参数

| 名称 | 是否必需 | 类型 | 描述 |
| :--- | :--- | :--- | :--- |
| `extid` | 是 | Int | 恢复被保持的通话。 |

### 实际示例

**请求示例**

```text
POST /api/v0.0.1/extension/unhold?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
    "extid": "101"
}
```



```text
POST /api/v0.0.1/extension/unhold?token=813b621cfe8eecf445a2ce1f4a079ffe&type=xml HTTP/1.1
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
	<status>Success</status>
</xml>
```

