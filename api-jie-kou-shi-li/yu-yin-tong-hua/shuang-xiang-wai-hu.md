---
description: 通过本接口可让 PBX 依次向外发起两路呼叫，并以 PBX 作为中间点建立连接，从而实现两个外部电话之间建立通话。
---

# 双向外呼



### 操作步骤

1. 拨打主叫号码，主叫摘机后听到回铃音。

* 拨打被叫号码，被叫响铃。被叫摘机后双方建立通话。

### 条件

* PBX 至少有两条空闲可用的中继。

### Endpoint

```text
POST /api/v0.0.1/outbound/dial_outbound?token={token}&type={type}
```

### 请求参数

| 名称 | 是否必需 | 类型 | 描述 |
| :--- | :--- | :--- | :--- |
| `caller` | 是 | String | 呼出的外线号码。 |
| `outto` | 是 | String | 呼出的外线号码。 |

### 响应参数

| 名称 | 类型 | 描述 |
| :--- | :--- | :--- |


### 实际示例

**请求示例**

```text
POST /api/v0.0.1/outbound/dial_outbound?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
	"caller":"16101",
	"outto":"16103"
}
```

```text
POST /api/v0.0.1/outbound/dial_outbound?token=813b621cfe8eecf445a2ce1f4a079ffe&type=xml HTTP/1.1
Content-Type:application/xml; charset=utf-8
Host: 172.16.6.150
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
	<caller>16101</caller>
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

