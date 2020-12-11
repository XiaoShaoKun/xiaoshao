---
description: 查询所有中继的基本信息，如：中继名、中继状态、中继类型等。
---

# 查询中继列表



### Endpoint

```text
POST /api/v0.0.1/trunklist/query?token={token}&type={type}
```

### 请求参数

无参数，直接发送查询中继列表请求即可。

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
      <td style="text-align:left"><code>trunklist</code>
      </td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left">&#x5BF9;&#x8C61;&#x53C2;&#x6570;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>trunkname</code>
      </td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">&#x4E2D;&#x7EE7;&#x540D;&#x79F0;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>type</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x4E2D;&#x7EE7;&#x7C7B;&#x578B;&#x3002;</p>
        <ul>
          <li>IAX&#xFF1A;IAX &#x534F;&#x8BAE;&#x7C7B;&#x578B;&#x7684; VoIP &#x4E2D;&#x7EE7;&#x3002;</li>
          <li>SIP&#xFF1A;SIP &#x534F;&#x8BAE;&#x7C7B;&#x578B;&#x7684; VoIP &#x4E2D;&#x7EE7;&#x3002;</li>
          <li>FXO&#xFF1A;FXO &#x6A21;&#x62DF;&#x4E2D;&#x7EE7;&#x3002;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>status</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>SIP/IAX &#x4E2D;&#x7EE7;&#x72B6;&#x6001;&#x3002;</p>
        <ul>
          <li>Registering&#xFF1A;&#x6CE8;&#x518C;&#x4E2D;</li>
          <li>Failure&#xFF1A;&#x6CE8;&#x518C;&#x5931;&#x8D25;</li>
          <li>Registered&#xFF1A;&#x5DF2;&#x6CE8;&#x518C;</li>
          <li>Disable&#xFF1A;&#x7981;&#x7528;</li>
          <li>Unknown&#xFF1A;&#x672A;&#x77E5;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>port</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x4E2D;&#x7EE7;&#x7AEF;&#x53E3;&#x3002;</td>
    </tr>
  </tbody>
</table>

### 实际示例

**请求示例**

```text
POST /api/v0.0.1/trunklist/query?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
```

```text
POST /api/v0.0.1/trunklist/query?token=813b621cfe8eecf445a2ce1f4a079ffe&type=xml HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
```

**响应示例**

```text
HTTP/1.1 200 OK
Access-control-allow-origin: *
Access-control-allow-methods: GET, POST, OPTIONS, PUT, DELETE
{
    "status": "Success",
    "trunkname": [
        {
            "trunkname": "to-108-16",
            "status": "Registered",
            "type": "SIP"
        },
        {
            "trunkname": "to-18-16-2",
            "status": "Registered",
            "type": "SIP"
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
    <trunkname>
        <item id="0">
            <trunkname>to-18-16-2</trunkname>
            <status>Registered</status>
            <type>SIP</type>
        </item>
    </trunkname>
</xml>
```

