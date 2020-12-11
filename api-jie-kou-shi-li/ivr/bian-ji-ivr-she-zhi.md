---
description: 修改 IVR 的配置，如：修改 IVR 号码、名称等。
---

# 编辑 IVR 设置



### Endpoint

```text
POST /api/v0.0.1/ivr/update?token={token}&type={type}
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
      <td style="text-align:left"><code>ivrid</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x8981;&#x914D;&#x7F6E;&#x7684; IVR &#x552F;&#x4E00;&#x6807;&#x8BC6;&#xFF08;IVR
        &#x53F7;&#x7801;&#xFF09;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ivrname</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>IVR &#x540D;&#x79F0;&#x3002;&#x9650;&#x5236;&#xFF1A;</p>
        <ul>
          <li>&#x4E0D;&#x5141;&#x8BB8;&#x8F93;&#x5165;<code>! $ ( ) / # ; , [ ] &quot; = &lt; &gt; &amp; &apos; ` ^ % @ { } | </code>&#x548C;&#x7A7A;&#x683C;&#x3002;</li>
          <li>&#x6700;&#x5927;31&#x4F4D;&#x3002;</li>
          <li>&#x4E0D;&#x80FD;&#x4E3A;&#x7A7A;&#x3002;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>promptrepeat</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x63D0;&#x793A;&#x97F3;&#x64AD;&#x653E;&#x6B21;&#x6570;</p>
        <p>&#x53EF;&#x9009;&#x62E9;&#x7684;&#x503C;&#xFF1A;1&#x3001;2&#x3001;3&#x3001;4&#x3001;5</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>responsetimeout</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">
        <p>&#x54CD;&#x5E94;&#x8D85;&#x65F6;&#x65F6;&#x95F4;</p>
        <p>&#x53EF;&#x9009;&#x62E9;&#x7684;&#x503C;&#xFF1A;1&#x3001;2&#x3001;3&#x3001;4&#x3001;5&#x3001;6&#x3001;7&#x3001;8&#x3001;9&#x3001;10</p>
      </td>
    </tr>
  </tbody>
</table>

### 实际示例

**请求示例**修改 IVR 4 的 IVR 号码为test\_ivr，promptrepeat为3，responsetimeout为5。

```text
POST /api/v1.1.0/ivr/update?token=1e3b3ebb6a974cb42ed31de5413df52d&type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 192.168.5.150
{
    "ivrid": "4",
    "ivrname": "test_ivr",
    "promptrepeat":"3",
    "responsetimeout":"5"
}
```

```text
POST /api/v1.1.0/ivr/update?token=1e3b3ebb6a974cb42ed31de5413df52d&type=xml HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 192.168.5.150
<?xml version="1.0" encoding="utf-8"?>
<xml>
	<ivrid>4</ivrid>
	<ivrname>test_ivr</ivrname>
	<promptrepeat>3</promptrepeat>
	<responsetimeout>5</responsetimeout>
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

