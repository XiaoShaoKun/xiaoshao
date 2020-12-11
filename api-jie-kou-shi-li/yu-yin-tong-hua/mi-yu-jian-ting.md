---
description: 通过本接口可让一个分机密语监听另一个分机的通话，即：监听方和被监听方两个分机之间可以互相通话，但是被监听分机的通话方不能和监听方通话。
---

# 密语监听



### 监听步骤

1. 分机 A 当前空闲，分机 B 正在通话中（可通过查询分机列表获取分机状态）。
2. 执行分机 A 密语监听分机 B 的命令。
3. 执行成功时，分机 A 自动应答后即可密语监听分机 B 的通话。注： 有的话机或软电话可能不支持自动应答，则话机或软电话会先响铃，手动接听后开始监听。

### 密语监听条件

* 监听方的监听方式必须是密语监听或为通用模式。
* 被监听方必须开启允许被监听。
* 只能监听同一台 PBX 设备上的分机。

### Endpoint

```text
POST /api/v0.0.1/extension/whisper?token={token}&type={type}
```

### 请求参数

| 名称 | 是否必需 | 类型 | 描述 |
| :--- | :--- | :--- | :--- |
| `whisperer` | 是 | Int | 密语监听的分机号。 |
| `whisperedext` | 是 | Int | 被监听的分机号。 |

### 实际示例

**请求示例**

```text
POST /api/v1.1.0/extension/whisper?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
    "whisperer": "101",
    "whisperedext": "106"
}
```

```text
POST /api/v1.1.0/extension/whisper?token=813b621cfe8eecf445a2ce1f4a079ffe&type=xml HTTP/1.1
Content-Type:application/xml; charset=utf-8
Host: 172.16.6.150
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
	<whisperer>101</whisperer>
	<whisperedext>106</whisperedext>
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

