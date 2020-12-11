---
description: 通过此接口，可以将指定动态坐席签出指定队列。
---

# 签出队列



### Endpoint

```text
POST /api/v0.0.1/queue/del_dynamicagent?token={token}&type={type}
```

### 请求参数

| 名称 | 是否必需 | 类型 | 描述 |
| :--- | :--- | :--- | :--- |
| `queueid` | 是 | Int | 请求时的队列号码。 |
| `extid` | 是 | Int | 动态坐席的号码。 |
| `password` | 是 | Int | 队列的密码。 |

### 实际示例

**请求示例**请求将坐席6000 签出队列9998；队列的密码为666666。

```text
POST /api/v1.1.0/queue/del_dynamicagent?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
	"queueid":"9998",
	"extid":"6000",
	"password":"666666"
}
```

```text
POST /api/v1.1.0/queue/del_dynamicagent?token=813b621cfe8eecf445a2ce1f4a079ffe&type=xml HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
	<queueid>9998</queueid>
	<extid>6000</extid>
	<password>666666</password>	
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

