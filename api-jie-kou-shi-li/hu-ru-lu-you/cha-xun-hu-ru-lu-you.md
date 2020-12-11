---
description: 查询单个呼入路由、多个呼入路由或所有呼入路由的设置。
---

# 查询呼入路由



### Endpoint

```text
POST /api/v0.0.1/inroute/query?token={token}&type={type}
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
            <p><b>&#x67E5;&#x8BE2;&#x5355;&#x4E2A;&#x547C;&#x5165;&#x8DEF;&#x7531;</b>&#xFF1A;&#x8BBE;&#x7F6E; <code>name</code> &#x4E3A;&#x547C;&#x5165;&#x8DEF;&#x7531;&#x7684;&#x540D;&#x79F0;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;name&quot;:&quot;route1&quot;</code>
            </p>
          </li>
          <li>
            <p><b>&#x67E5;&#x8BE2;&#x591A;&#x4E2A;&#x547C;&#x5165;&#x8DEF;&#x7531;</b>&#xFF1A;&#x8BBE;&#x7F6E; <code>name</code> &#x4E3A;&#x547C;&#x5165;&#x8DEF;&#x7531;&#x7684;&#x540D;&#x79F0;&#xFF0C;&#x591A;&#x4E2A;&#x547C;&#x5165;&#x8DEF;&#x7531;&#x4E4B;&#x95F4;&#x7528; <code>,</code> &#x9694;&#x5F00;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;name&quot;: &quot;route1,route2&quot;</code>
            </p>
          </li>
          <li><b>&#x67E5;&#x8BE2;&#x6240;&#x6709;&#x547C;&#x5165;&#x8DEF;&#x7531;</b>&#xFF1A;&#x8BBE;&#x7F6E; <code>name</code>&#x4E3A;<code>all</code>&#x3002;</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

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
      <td style="text-align:left"><code>inroutes</code>
      </td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left">&#x5BF9;&#x8C61;&#x53C2;&#x6570;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>id</code>
      </td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">&#x547C;&#x5165;&#x8DEF;&#x7531;&#x7684;&#x6807;&#x8BC6;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>name</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x547C;&#x5165;&#x8DEF;&#x7531;&#x7684;&#x540D;&#x79F0;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>did</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">DID &#x5339;&#x914D;&#x6A21;&#x5F0F;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>caller_id</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x6765;&#x7535;&#x5339;&#x914D;&#x6A21;&#x5F0F;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>desttype</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x76EE;&#x7684;&#x5730;&#x7C7B;&#x578B;&#x3002;</p>
        <ul>
          <li>hangup&#xFF1A;&#x6302;&#x65AD;</li>
          <li>extension&#xFF1A;&#x5206;&#x673A;</li>
          <li>voicemail&#xFF1A;&#x8BED;&#x97F3;&#x90AE;&#x7BB1;</li>
          <li>ivr&#xFF1A;IVR</li>
          <li>ringgroup&#xFF1A;&#x54CD;&#x94C3;&#x7EC4;</li>
          <li>queue&#xFF1A;&#x961F;&#x5217;</li>
          <li>conference&#xFF1A;&#x4F1A;&#x8BAE;&#x5BA4;</li>
          <li>disa&#xFF1A;DISA</li>
          <li>callback&#xFF1A;&#x56DE;&#x62E8;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>dest</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x5177;&#x4F53;&#x76EE;&#x7684;&#x5730;&#x3002;</td>
    </tr>
  </tbody>
</table>

### 实际示例

**请求示例**

```text
POST /api/v0.0.1/inroute/query?token=277ac400357b509b4a587ff2157f7ad5&type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
    "name": "all"
}
```

```text
POST /api/v0.0.1/inroute/query?token=277ac400357b509b4a587ff2157f7ad5&type=xml HTTP/1.1
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
<?xml version="1.0" encoding="utf-8"?>
<xml>
    <status>Success</status>
    <inroutes>
        <item id="0">
            <id></id>
            <name>test</name>
            <did></did>
            <caller_id></caller_id>
            <desttype>extension</desttype>
            <dest>102</dest>
        </item>
    </inroutes>
</xml>
```

```text
HTTP/1.1 200 OK
Access-control-allow-origin: *
Access-control-allow-methods: GET, POST, OPTIONS, PUT, DELETE
{
    "status": "Success",
    "inroutes": [
        {
            "id": "",
            "name": "test",
            "did": "",
            "caller_id": "",
            "desttype": "extension",
            "dest": "102"
        }
    ]
}
```

