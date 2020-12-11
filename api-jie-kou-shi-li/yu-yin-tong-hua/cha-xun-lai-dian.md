---
description: 查询当前外部来电的详细信息，如：主叫、被叫、通话状态、通过的中继等。
---

# 查询来电



### Endpoint

```text
POST /api/v0.0.1/inbound/query?token={token}&type={type}
```

### 请求参数

* 带参数表示查询单个或多个，多个时需用 `,` 隔开。

| 名称 | 是否必需 | 类型 | 描述 |
| :--- | :--- | :--- | :--- |
| `inboundid` | 是 | Int | 外线来电编号。注： 从 PBX 发送的通话报告中获取 `inboundid` 的值。 |

### 响应参数

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x540D;&#x79F0;</th>
      <th style="text-align:left">&#x7C7B;&#x578B;</th>
      <th style="text-align:left">&#x63CF;&#x8FF0;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>inbound</code>
      </td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left">&#x6765;&#x7535;&#xFF0C;&#x7531;&#x5916;&#x7EBF;&#x547C;&#x5165;&#x7684;&#x5916;&#x90E8;&#x901A;&#x8BDD;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>inboundid</code>
      </td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">&#x5916;&#x7EBF;&#x6765;&#x7535;&#x7F16;&#x53F7;&#xFF0C;&#x901A;&#x8FC7;&#x8BE5;&#x53C2;&#x6570;&#x5BF9;&#x6765;&#x7535;&#x8FDB;&#x884C;&#x8F6C;&#x63A5;&#x3001;&#x67E5;&#x8BE2;&#x3001;&#x6302;&#x65AD;&#x7B49;&#x64CD;&#x4F5C;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>from</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x4E3B;&#x53EB;&#x53F7;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>to</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x88AB;&#x53EB;&#x53F7;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>callee</code>
      </td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left">&#x6765;&#x7535;&#x7684;&#x901A;&#x8BDD;&#x65B9;&#xFF0C;&#x53EF;&#x80FD;&#x4E3A;&#x5206;&#x673A;&#x3001;IVR&#x3001;&#x53BB;&#x7535;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>trunk</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x547C;&#x5165;&#x65F6;&#x901A;&#x8FC7;&#x7684;&#x4E2D;&#x7EE7;&#x540D;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>status</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x901A;&#x8BDD;&#x72B6;&#x6001;</p>
        <ul>
          <li>Talking&#xFF1A;&#x901A;&#x8BDD;&#x8FDB;&#x884C;&#x4E2D;&#x3002;</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

### 实际示例

**请求示例**

```text
POST /api/v0.0.1/inbound/query?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
	"inboundid":"1589879501.901"
}
```

```text
POST /api/v0.0.1/inbound/query?token=813b621cfe8eecf445a2ce1f4a079ffe&type=xml HTTP/1.1
Content-Type:application/xml; charset=utf-8
Host: 172.16.6.150
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
    <inboundid>1589879501.901</inboundid>
</xml>
```

**响应示例**

```text
HTTP/1.1 200 OK
Access-control-allow-origin: *
Access-control-allow-methods: GET, POST, OPTIONS, PUT, DELETE
{
    "status": "Success",
    "inbound": [
        {
            "inboundid": "1589881290.963",
            "from": "103",
            "to": "101",
            "trunk": "to-18-16-2",
            "callee": {
                "extid": "101"
            },
            "status": "Talking"
        }
    ]
}
```

```text
HTTP/1.1 200 OK
Access-control-allow-origin: *
Access-control-allow-methods: GET, POST, OPTIONS, PUT, DELETE
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
	<status>Success</status>
	<inbound>
		<inboundid>1589881290.963</inboundid>
		<from>103</from>
		<to>101</to>
		<trunk>to-18-16-2</trunk>
		<callee>
			<extid>101</extid>
		</callee>
		<status>Talking</status>
	</inbound>
</xml>
```

