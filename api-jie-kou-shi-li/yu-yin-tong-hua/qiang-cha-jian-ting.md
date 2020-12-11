---
description: 通过本接口可让一个分机强制插入到另一个分机的通话中去，从而形成三方通话。
---

# 强插监听



### 监听步骤

1. 分机 A 当前空闲，分机 B 正在通话中（可通过查询分机列表获取分机状态）。
2. 执行分机 A 强插监听分机 B 的命令。
3. 执行成功时，分机 A 自动应答后即可强插到分机 B 的通话中。注： 有的话机或软电话可能不支持自动应答，则话机或软电话会先响铃，手动接听后开始监听。

### 强插监听条件

* 监听方监听方式必须是强插监听或为通用模式。
* 被监听方必须开启允许被监听。
* 只能监听同一台 IPPBX 设备上的分机。

### Endpoint

```text
POST /api/v0.0.1/extension/barge?token={token}&type={type}
```

### 请求参数

| 名称 | 是否必需 | 类型 | 描述 |
| :--- | :--- | :--- | :--- |
| `bargein` | 是 | Int | 强插监听的分机号。 |
| `bargedext` | 是 | Int | 被监听的分机号。 |

### 实际示例

**请求示例**

```text
POST /api/v0.0.1/extension/barge?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
    "bargein": "101",
    "bargedext": "106"
}
```

```text
POST /api/v0.0.1/extension/barge?token=813b621cfe8eecf445a2ce1f4a079ffe&type=xml HTTP/1.1
Content-Type:application/xml; charset=utf-8
Host: 172.16.6.150
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
	<bargein>101</bargein>
	<bargedext>106</bargedext>
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

