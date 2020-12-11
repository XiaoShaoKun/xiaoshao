---
description: 查询当前 IPPBX 系统分机通过外线呼出的所有通话的详细信息，如：主叫、被叫、通话状态、通过的中继、目的地等。
---

# 查询去电



### Endpoint

```text
POST /api/v0.0.1/outbound/query?token={token}&type={type}
```

### 请求参数

* 带参数表示查询单个或多个，多个时需用 `,`隔开。

| 名称 | 是否必需 | 类型 | 描述 |
| :--- | :--- | :--- | :--- |
| `outboundid` | 否 | Int | 外线去电编号。注： 从 PBX 发送的通话报告 中获取 `outboundid` 的值。 |

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
      <td style="text-align:left"><code>outbound</code>
      </td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left">&#x53BB;&#x7535;&#xFF0C;&#x4E3A;&#x547C;&#x51FA;&#x5230;&#x5916;&#x7EBF;&#x7684;&#x5916;&#x90E8;&#x901A;&#x8BDD;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>outboundid</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x5916;&#x7EBF;&#x53BB;&#x7535;&#x7F16;&#x53F7;&#xFF0C;&#x901A;&#x8FC7;&#x8BE5;&#x53C2;&#x6570;&#x5BF9;&#x53BB;&#x7535;&#x8FDB;&#x884C;&#x8F6C;&#x63A5;&#x3001;&#x67E5;&#x8BE2;&#x3001;&#x6302;&#x65AD;&#x7B49;&#x64CD;&#x4F5C;&#x3002;</td>
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
      <td style="text-align:left"><code>trunk</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x547C;&#x51FA;&#x65F6;&#x901A;&#x8FC7;&#x7684;&#x4E2D;&#x7EE7;&#x540D;&#x79F0;&#x3002;</td>
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
POST /api/v0.0.1/outbound/query?token=1e3b3ebb6a974cb42ed31de5413df52d&type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 192.168.5.150
{
    "outboundid": "1495705009.316"
}
```

```text
POST /api/v0.0.1/outbound/query?token=1e3b3ebb6a974cb42ed31de5413df52d&type=xml HTTP/1.1
Content-Type:application/xml; charset=utf-8
Host: 192.168.5.150
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
    <outboundid>1495705009.316</outboundid>
</xml>
```

**响应示例**

```text
HTTP/1.1 200 OK
Access-control-allow-origin: *
Access-control-allow-methods: GET, POST, OPTIONS, PUT, DELETE
{
    "status": "Success",
    "outbound": [
        {
            "outboundid": "1589881535.982",
            "from": "66666",
            "to": "103",
            "trunk": "to-18-16-2",
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
	<outbound>
		<outboundid>1589881535.982</outboundid>
		<from>66666</from>
		<to>103</to>
		<trunk>to-18-16-2</trunk>
		<status>Talking</status>
	</outbound>
</xml>
```

