---
description: 通过本接口可以实现一个分机监听另一个分机的当前通话。
---

# 普通监听



### 监听步骤

1. 分机 A 空闲，分机 B 正在通话，（可通过查询分机列表获取分机状态）。
2. 执行分机 A 普通监听分机 B 的命令，即分机 A 可以监听到分机 B 和分机 B 的通话方，但是分机 B 和分机B 的通话方听不到分机 A 的声音。
3. 执行成功时，分机 A 自动应答后即可监听到分机 B 的通话内容。

注： 有的话机或软电话可能不支持自动应答，则话机或软电话会先响铃，手动接听后开始监听。

### **普通监听条件**

* 监听方的监听方式为普通监听或为通用模式。
* 被监听方必须开启允许被监听，否则不能被监听；一个分机最多只能同时被一个分机监听。
* 只能监听同一台 IPPBX 上的分机。

### Endpoint

```text
POST /api/v0.0.1/extension/listen?token={token}&type={type}
```

### 请求参数

| 名称 | 是否必需 | 类型 | 描述 |
| :--- | :--- | :--- | :--- |
| `listener` | 是 | Int | 监听的分机号。 |
| `listenedext` | 是 | Int | 被监听的分机号。 |

### 实际示例

**请求示例**

分机101 监听分机106的通话。

```text
POST /api/v0.0.1/extension/listen?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
    "listener": "101",
    "listenedext": "106"
}
```

```text
POST /api/v0.0.1/extension/listen?token=813b621cfe8eecf445a2ce1f4a079ffe&type=xml HTTP/1.1
Content-Type:application/xml; charset=utf-8
Host: 172.16.6.150
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
	<listener>101</listener>
	<listenedext>106</listenedext>
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

