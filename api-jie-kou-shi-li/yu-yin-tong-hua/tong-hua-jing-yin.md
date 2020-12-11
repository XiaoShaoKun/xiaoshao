---
description: >-
  PBX
  分机通话时，可利用该接口将分机静音。即分机的通话方不能听到分机的声音，而分机可以听到对方的声音。如需取消静音，请使用取消静音接口。通话结束后，分机也会自动取消静音。
---

# 通话静音



### Endpoint

```text
POST /api/v0.0.1/extension/mute?token={token}&type={type}
```

### 请求参数

| 名称 | 是否必需 | 类型 | 描述 |
| :--- | :--- | :--- | :--- |
| `extid` | 是 | Int | 要静音分机的分机号。 |

### 实际示例

**请求示例**请求将分机101的通话静音。

```text
POST /api/v0.0.1/extension/mute?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
    "extid": "101"
}
```

```text
POST /api/v0.0.1/extension/mute?token=813b621cfe8eecf445a2ce1f4a079ffe&type=xml HTTP/1.1
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

