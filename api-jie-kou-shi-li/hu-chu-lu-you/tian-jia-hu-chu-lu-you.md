---
description: 添加并设置呼出路由。
---

# 添加呼出路由



### Endpoint

```text
POST /api/v0.0.1/outroute/add?token={token}&type={type}
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
      <td style="text-align:left">&#x547C;&#x51FA;&#x8DEF;&#x7531;&#x7684;&#x540D;&#x79F0;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>prefix</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x524D;&#x7F00;&#x5220;&#x9664;&#x6210;&#x529F;&#x7684;&#x5339;&#x914D;&#x3002;&#x62E8;&#x6253;&#x7684;&#x53F7;&#x7801;&#x4E0E;&#x6B64;&#x4EE5;&#x53CA;&#x968F;&#x540E;&#x7684;&#x5217;&#x8FDB;&#x884C;&#x6BD4;&#x8F83;&#x3002;&#x5728;&#x5339;&#x914D;&#x4E4B;&#x540E;&#xFF0C;&#x5728;&#x5C06;&#x524D;&#x7F00;&#x53D1;&#x9001;&#x5230;&#x4E2D;&#x7EE7;&#x4E4B;&#x524D;&#xFF0C;&#x5C06;&#x8BE5;&#x524D;&#x7F00;&#x4ECE;&#x6240;&#x62E8;&#x53F7;&#x7801;&#x4E2D;&#x79FB;&#x9664;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>matchpattern</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x6240;&#x62E8;&#x53F7;&#x7801;&#x5C06;&#x4E0E;&#x524D;&#x7F00;+&#x6B64;&#x5339;&#x914D;&#x6A21;&#x5F0F;&#x8FDB;&#x884C;&#x6BD4;&#x8F83;&#x3002;&#x4E00;&#x65E6;&#x5339;&#x914D;&#xFF0C;&#x6240;&#x62E8;&#x53F7;&#x7801;&#x7684;&#x5339;&#x914D;&#x6A21;&#x5F0F;&#x90E8;&#x5206;&#x5C06;&#x88AB;&#x53D1;&#x9001;&#x5230;&#x4E2D;&#x7EE7;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>prepend</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x6570;&#x5B57;&#x9884;&#x5148;&#x5339;&#x914D;&#x6210;&#x529F;&#x3002;&#x5982;&#x679C;&#x62E8;&#x6253;&#x7684;&#x53F7;&#x7801;&#x4E0E;&#x540E;&#x7EED;&#x5217;&#x6307;&#x5B9A;&#x7684;&#x6A21;&#x5F0F;&#x76F8;&#x5339;&#x914D;&#xFF0C;&#x5219;&#x5728;&#x53D1;&#x9001;&#x5230;&#x4E2D;&#x7EE7;&#x4E4B;&#x524D;&#xFF0C;&#x8FD9;&#x5C06;&#x88AB;&#x524D;&#x7F6E;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>callerid</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x5982;&#x679C;&#x63D0;&#x4F9B;&#x4E86;&#x4E3B;&#x53EB;&#x65B9;&#x53F7;&#x7801;&#xFF0C;&#x88AB;&#x53EB;&#x53F7;&#x7801;&#x5C06;&#x53EA;&#x5339;&#x914D;&#x524D;&#x7F00;+&#x5339;&#x914D;&#x6A21;&#x5F0F;&#xFF0C;&#x5982;&#x679C;&#x53D1;&#x9001;&#x7684;&#x4E3B;&#x53EB;&#x65B9;ID&#x4E0E;&#x6B64;&#x5339;&#x914D;&#x3002;&#x5F53;&#x5206;&#x673A;&#x62E8;&#x6253;&#x5916;&#x90E8;&#x7535;&#x8BDD;&#x65F6;&#xFF0C;&#x6765;&#x7535;&#x663E;&#x793A;&#x5C06;&#x662F;&#x4ED6;&#x4EEC;&#x7684;&#x5206;&#x673A;&#x53F7;&#x7801;&#xFF0C;&#x800C;&#x4E0D;&#x662F;&#x4ED6;&#x4EEC;&#x7684;&#x51FA;&#x5C40;CID&#x3002;&#x4EE5;&#x4E0A;&#x7279;&#x6B8A;&#x5339;&#x914D;&#x5E8F;&#x5217;&#x53EF;&#x7528;&#x4E8E;&#x4E0E;&#x5176;&#x5B83;&#x53F7;&#x7801;&#x5339;&#x914D;&#x7C7B;&#x4F3C;&#x7684;&#x6765;&#x7535;&#x53F7;&#x7801;&#x5339;&#x914D;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>trunks</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x4E2D;&#x7EE7;&#x540D;&#x79F0;&#x3002;</p>
        <p>&#x591A;&#x4E2A;&#x4E2D;&#x7EE7;&#x4E4B;&#x95F4;&#x7528; , &#x9694;&#x5F00;&#xFF0C;&#x4F8B;&#x5982;
          &quot;trunks&quot;:&quot;trunk1,trunk2&quot;</p>
      </td>
    </tr>
  </tbody>
</table>

### 实际示例

**请求示例**

```text
POST /api/v0.0.1/outroute/add?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
    "name":"to16",
    "matchpattern":"X.",
    "prefix":"16",
    "trunks":"to-18-16-2"
}
```

```text
POST /api/v0.0.1/outroute/add?token=813b621cfe8eecf445a2ce1f4a079ffe&type=xml HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
	<name>to16</name>
	<matchpattern>X.</matchpattern>
	<prefix>16</prefix>
	<trunks>to-18-16-2</trunks>
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

