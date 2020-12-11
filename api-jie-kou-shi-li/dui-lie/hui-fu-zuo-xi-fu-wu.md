---
description: 恢复某个坐席的服务。坐席被恢复之后，可以接听到呼入到该队列的来电。
---

# 恢复坐席服务



### Endpoint

```text
POST /api/v0.0.1/queue/unpause_agent?token={token}&type={type}
```

### 请求参数

| **名称** | **是否必需** | **类型** | **描述** |
| :--- | :--- | :--- | :--- |
| `queueid` | 是 | Int | 队列号码。 |
| `extid` | 是 | Int | 坐席号码。 |

### 实际示例

**请求示例**请求恢复坐席1000的服务。

```text
POST /api/v0.0.1/queue/unpause_agent?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
    "queueid": "9998",
    "extid": "6000"
}
```

```text
POST /api/v0.0.1/queue/unpause_agent?token=813b621cfe8eecf445a2ce1f4a079ffe&type=xml HTTP/1.1
Content-Type:application/xml; charset=utf-8
Host: 172.16.6.150
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
	<queueid>9998</queueid>
	<extid>6000</extid>	
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
<?xml version="1.0" encoding="utf-8"?>
<xml>
	<status>Success</status>
</xml>
```



