---
description: 删除单个 SIP 中继、多个 SIP 中继或所有 SIP 中继。
---

# 删除 SIP 中继



### Endpoint

```text
POST /api/v0.0.1/siptrunk/delete?token={token}&type={type}
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
      <td style="text-align:left"><code>trunkname</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>SIP &#x4E2D;&#x7EE7;&#x7684;&#x540D;&#x79F0;&#x3002;</p>
        <ul>
          <li>
            <p><b>&#x5220;&#x9664;&#x5355;&#x4E2A; SIP &#x4E2D;&#x7EE7;</b>&#xFF1A;&#x8BBE;&#x7F6E; <code>trunkname</code> &#x4E3A;
              SIP &#x4E2D;&#x7EE7;&#x540D;&#x79F0;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;trunkname&quot;:&quot;SIP&quot;</code>
            </p>
          </li>
          <li>
            <p><b>&#x5220;&#x9664;&#x591A;&#x4E2A; SIP &#x4E2D;&#x7EE7;</b>&#xFF1A;&#x8BBE;&#x7F6E; <code>trunkname</code> &#x4E3A;
              SIP &#x4E2D;&#x7EE7;&#x540D;&#x79F0;&#xFF0C;&#x591A;&#x4E2A; SIP &#x4E2D;&#x7EE7;&#x4E4B;&#x95F4;&#x7528; <code>,</code> &#x9694;&#x5F00;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;trunkname&quot;: &quot;SIP,siptrunk&quot;</code>
            </p>
          </li>
          <li><b>&#x5220;&#x9664;&#x6240;&#x6709;SIP&#x4E2D;&#x7EE7;</b>&#xFF1A;&#x8BBE;&#x7F6E; <code>trunkname</code>&#x4E3A;<code>all</code>&#x3002;</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

### 实际示例

**请求示例**

```text
POST /api/v0.0.1/siptrunk/delete?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
    "trunkname": "to-108-16"
}
```

```text
POST /api/v0.0.1/siptrunk/delete?token=813b621cfe8eecf445a2ce1f4a079ffe&type=xml HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
	<trunkname>to-108-16</trunkname>
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
<?xml version="1.0" encoding="utf-8"?>
<xml>
	<status>Success</status>
</xml>
```

