---
description: 删除单个呼入路由、多个呼入路由或所有呼入路由。
---

# 删除呼入路由



### Endpoint

```text
POST /api/v0.0.1/inroute/delete?token={token}&type={type}
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
        <p>&#x547C;&#x5165;&#x8DEF;&#x7531;&#x7684;&#x540D;&#x79F0;&#x3002;</p>
        <ul>
          <li>
            <p><b>&#x5220;&#x9664;&#x5355;&#x4E2A;&#x547C;&#x5165;&#x8DEF;&#x7531;</b>&#xFF1A;&#x8BBE;&#x7F6E; <code>name</code> &#x4E3A;&#x547C;&#x5165;&#x8DEF;&#x7531;&#x7684;&#x540D;&#x79F0;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;name&quot;:&quot;route1&quot;</code>
            </p>
          </li>
          <li>
            <p><b>&#x5220;&#x9664;&#x591A;&#x4E2A;&#x547C;&#x5165;&#x8DEF;&#x7531;</b>&#xFF1A;&#x8BBE;&#x7F6E; <code>name</code> &#x4E3A;&#x547C;&#x5165;&#x8DEF;&#x7531;&#x7684;&#x540D;&#x79F0;&#xFF0C;&#x591A;&#x4E2A;&#x547C;&#x5165;&#x8DEF;&#x7531;&#x4E4B;&#x95F4;&#x7528; <code>,</code> &#x9694;&#x5F00;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;name&quot;: &quot;route1,route2&quot;</code>
            </p>
          </li>
          <li><b>&#x5220;&#x9664;&#x6240;&#x6709;&#x547C;&#x5165;&#x8DEF;&#x7531;</b>&#xFF1A;&#x8BBE;&#x7F6E; <code>name</code> &#x4E3A; <code>all</code>&#x3002;</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

### 实际示例

**请求示例**

```text
POST /api/v0.0.1/inroute/delete?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
    "name":"test2"
}
```

```text
POST /api/v0.0.1/inroute/delete?token=813b621cfe8eecf445a2ce1f4a079ffe&type=xml HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
	<name>test2</name>	
</xml>
```

**响应示例**

```text
HTTP/1.1 200 OK
Access-control-allow-origin: *
Access-control-allow-methods: GET, POST, OPTIONS, PUT, DELETE
<?xml version="1.0" encoding="utf-8"?>
<xml>
	<status>Success</status>
</xml>
```

