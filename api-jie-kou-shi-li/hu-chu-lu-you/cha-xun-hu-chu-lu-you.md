---
description: 查询单个呼出路由、多个呼出路由或所有呼出路由的设置。
---

# 查询呼出路由



### Endpoint

```text
POST /api/v0.0.1/outroute/query?token={token}&type={type}
```

### 请求参数

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x540D;&#x79F0;</th>
      <th style="text-align:left">&#x662F;&#x5426;&#x5FC5;&#x9700;</th>
      <th style="text-align:left">&#x7C7B;&#x578B;</th>
      <th style="text-align:left">&#x63CF;&#x8FF0;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>name</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x547C;&#x51FA;&#x8DEF;&#x7531;&#x7684;&#x540D;&#x79F0;&#x3002;</p>
        <ul>
          <li>
            <p><b>&#x67E5;&#x8BE2;&#x5355;&#x4E2A;&#x547C;&#x51FA;&#x8DEF;&#x7531;</b>&#xFF1A;&#x8BBE;&#x7F6E; <code>name</code> &#x4E3A;&#x547C;&#x51FA;&#x8DEF;&#x7531;&#x7684;&#x540D;&#x79F0;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;name&quot;:&quot;route1&quot;</code>
            </p>
          </li>
          <li>
            <p><b>&#x67E5;&#x8BE2;&#x591A;&#x4E2A;&#x547C;&#x51FA;&#x8DEF;&#x7531;</b>&#xFF1A;&#x8BBE;&#x7F6E; <code>name</code> &#x4E3A;&#x547C;&#x51FA;&#x8DEF;&#x7531;&#x7684;&#x540D;&#x79F0;&#xFF0C;&#x591A;&#x4E2A;&#x547C;&#x51FA;&#x8DEF;&#x7531;&#x4E4B;&#x95F4;&#x7528; <code>,</code> &#x9694;&#x5F00;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;name&quot;: &quot;route1,route2&quot;</code>
            </p>
          </li>
          <li><b>&#x67E5;&#x8BE2;&#x6240;&#x6709;&#x547C;&#x51FA;&#x8DEF;&#x7531;</b>&#xFF1A;&#x8BBE;&#x7F6E; <code>name</code> &#x4E3A;<code>all</code>&#x3002;</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

### 响应参数

| 名称 | 类型 | 描述 |
| :--- | :--- | :--- |
| `outroutes` | Object | 对象参数。 |
| `id` | Int | 呼出路由的标识码。 |
| `name` | String | 呼出路由的名称。 |
| `prefix` | String | 前缀删除成功的匹配。拨打的号码与此以及随后的列进行比较。在匹配之后，在将前缀发送到中继之前，将该前缀从所拨号码中移除。 |
| `prepend` | String | 数字预先匹配成功。如果拨打的号码与后续列指定的模式相匹配，则在发送到中继之前，这将被前置。 |
| `matchpattern` | String | 所拨号码将与前缀+此匹配模式进行比较。一旦匹配，所拨号码的匹配模式部分将被发送到中继。 |
| `callerid` | String | 如果提供了主叫方号码，被叫号码将只匹配前缀+匹配模式，如果发送的主叫方ID与此匹配。当分机拨打外部电话时，来电显示将是他们的分机号码，而不是他们的出局CID。以上特殊匹配序列可用于与其它号码匹配类似的来电号码匹配。 |
| `trunks` | String | 中继名称。 |

### 实际示例

**请求示例**

```text
POST /api/v0.0.1/outroute/query?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
    "name":"all"
}
```

```text
POST /api/v0.0.1/outroute/query?token=813b621cfe8eecf445a2ce1f4a079ffe&type=xml HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
	<name>all</name>	
</xml>

```

**响应示例**

```text
HTTP/1.1 200 OK
Access-control-allow-origin: *
Access-control-allow-methods: GET, POST, OPTIONS, PUT, DELETE
{
    "status": "Success",
    "outroutes": [
        {
            "id": "19",
            "name": "to-pbx",
            "prepend": "",
            "prefix": "16",
            "matchpattern": "X.",
            "callerid": "",
            "trunks": "to-18-16-2"
        }
    ]
}
```

```text
HTTP/1.1 200 OK
Access-control-allow-origin: *
Access-control-allow-methods: GET, POST, OPTIONS, PUT, DELETE
<?xml version="1.0" encoding="utf-8"?>
<xml>
	<status>Success</status>
	<outroutes>
		<item id="0">
			<id>19</id>
			<name>to-pbx</name>
			<prepend></prepend>
			<prefix>16</prefix>
			<matchpattern>X.</matchpattern>
			<callerid></callerid>
			<trunks>to-18-16-2</trunks>
		</item>
	</outroutes>
</xml>
```

