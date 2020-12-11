---
description: 查询 PBX 上分机列表的基本信息，如：分机名、分机号、分机状态、类型等。
---

# 查询分机列表



### Endpoint

```text
POST /api/v0.0.1/extensionlist/query?token={token}&type={type}
```

### 请求参数

无参数，直接发送查询分机列表的请求即可。

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
      <td style="text-align:left"><code>extlist</code>
      </td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left">&#x5206;&#x673A;&#x5BF9;&#x8C61;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>extnumber</code>
      </td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">&#x5206;&#x673A;&#x53F7;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>status</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x5206;&#x673A;&#x5F53;&#x524D;&#x72B6;&#x6001;&#xFF1A;</p>
        <ul>
          <li>Unavailable&#xFF1A;&#x4E0D;&#x53EF;&#x4F7F;&#x7528;&#x3002;</li>
          <li>Registered&#xFF1A;&#x5DF2;&#x6CE8;&#x518C;&#x3002;</li>
          <li>Ringing&#xFF1A;&#x54CD;&#x94C3;&#x3002;</li>
          <li>Busy&#xFF1A;&#x5FD9;&#x7EBF;&#x3002;</li>
          <li>Hold&#xFF1A;&#x901A;&#x8BDD;&#x4FDD;&#x6301;&#x3002;</li>
          <li>Malfunction&#xFF1A;&#x6545;&#x969C;&#x3002;</li>
          <li>Idle&#xFF1A;&#x7A7A;&#x95F2;&#x3002;</li>
          <li>Fxsnoport</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>type</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x5206;&#x673A;&#x7C7B;&#x578B;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>port</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x5206;&#x673A;&#x7AEF;&#x53E3;&#xFF0C;&#x5F53;&#x5206;&#x673A;&#x4E3A;&#x6A21;&#x62DF;&#x5206;&#x673A;&#x65F6;&#x5219;&#x663E;&#x793A;&#x8BE5;&#x9879;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>username</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x7528;&#x6237;&#x540D;&#x3002;</td>
    </tr>
  </tbody>
</table>

### 实际示例

**请求示例**

```text
POST /api/v0.0.1/extensionlist/query?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json HTTP/1.1 HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
```

```text
POST /api/v0.0.1/extensionlist/query?token=813b621cfe8eecf445a2ce1f4a079ffe&type=xml HTTP/1.1 HTTP/1.1
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
    "extlist": [
        {
            "extnumber": "100",
            "status": "Unavailable",
            "type": "pjsip",
            "username": "100",
            "agentid": ""
        },
        {
            "extnumber": "101",
            "status": "Registered",
            "type": "pjsip",
            "username": "xiaoshaokun",
            "agentid": ""
        },
        {
            "extnumber": "102",
            "status": "Registered",
            "type": "pjsip",
            "username": "102",
            "agentid": ""
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
    <extlist>
        <item id="0">
            <extnumber>100</extnumber>
            <status>Unavailable</status>
            <type>pjsip</type>
            <username>100</username>
            <agentid></agentid>
        </item>
        <item id="1">
            <extnumber>101</extnumber>
            <status>Unavailable</status>
            <type>pjsip</type>
            <username>xiaoshaokun</username>
            <agentid></agentid>
        </item>
        <item id="2">
            <extnumber>102</extnumber>
            <status>Unavailable</status>
            <type>pjsip</type>
            <username>102</username>
            <agentid></agentid>
        </item>
        <item id="3">
            <extnumber>103</extnumber>
            <status>Unavailable</status>
            <type>pjsip</type>
            <username>103</username>
            <agentid></agentid>
        </item>
      
    </extlist>
</xml>
```

