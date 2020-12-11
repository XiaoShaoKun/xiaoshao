---
description: 暂停某个坐席的服务。坐席被暂停之后，将不会接听到呼入到该队列的来电。
---

# 暂停坐席服务



### Endpoint

```text
POST /api/v0.0.1/queue/pause_agent?token={token}&type={type}
```

### 请求参数

| **名称** | **是否必需** | **类型** | **描述** |
| :--- | :--- | :--- | :--- |
| `queueid` | 是 | Int | 请求时的队列号码。 |
| `extid` | 是 | Int | 坐席的号码。 |

### 实际示例

**请求示例**

```text
POST /api/v0.0.1/queue/pause_agent?token=1e3b3ebb6a974cb42ed31de5413df52d&type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
    "queueid": "9998",
    "extid": "6000"
}
```



```text
POST /api/v0.0.1/queue/pause_agent?token=1e3b3ebb6a974cb42ed31de5413df52d&type=xml HTTP/1.1
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

