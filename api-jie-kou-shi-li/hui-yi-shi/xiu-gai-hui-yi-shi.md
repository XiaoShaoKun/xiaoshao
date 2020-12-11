---
description: 修改 PBX 网页已创建的会议室的配置。
---

# 修改会议室

### 请求地址

```text
POST /api/v0.0.1/conference/update?token={token}&type={type}
```

### 请求参数

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x53C2;&#x6570;</th>
      <th style="text-align:left">&#x662F;&#x5426;&#x5FC5;&#x9009;</th>
      <th style="text-align:left">&#x7C7B;&#x578B;</th>
      <th style="text-align:left">&#x63CF;&#x8FF0;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">number</td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x56FA;&#x5B9A;&#x4F1A;&#x8BAE;&#x5BA4;&#x53F7;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">name</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x56FA;&#x5B9A;&#x4F1A;&#x8BAE;&#x5BA4;&#x540D;&#x79F0;&#x3002;&#x6CE8;&#xFF1A;
        &#x4E0D;&#x5141;&#x8BB8;&#x8F93;&#x5165;&#x4EE5;&#x4E0B;&#x5B57;&#x7B26;&#xFF1A;<code>&amp;&apos;&lt;&gt;`|$]\&quot;</code>&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">participantepassword</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x4E0E;&#x4F1A;&#x8005;&#x5BC6;&#x7801;&#x3002;&#x6CE8;&#xFF1A; &#x53EA;&#x5141;&#x8BB8;&#x8F93;&#x5165;&#x6570;&#x5B57;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">moderatorpassword</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x4E3B;&#x6301;&#x4EBA;&#x5BC6;&#x7801;&#x3002;&#x6CE8;&#xFF1A; &#x53EA;&#x5141;&#x8BB8;&#x8F93;&#x5165;&#x6570;&#x5B57;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">waitformoderator</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x662F;&#x5426;&#x7B49;&#x5019;&#x4E3B;&#x6301;&#x4EBA;&#x8FDB;&#x5165;&#x540E;&#x624D;&#x5F00;&#x59CB;&#x4F1A;&#x8BAE;&#x3002;</p>
        <p><b>&#x53D6;&#x503C;&#x8303;&#x56F4;</b>&#xFF1A;</p>
        <ul>
          <li>yes&#xFF1A;&#x662F;&#x3002;</li>
          <li>no&#xFF1A;&#x5426;&#x3002;</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

### 响应参数

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x53C2;&#x6570;</th>
      <th style="text-align:left">&#x7C7B;&#x578B;</th>
      <th style="text-align:left">&#x63CF;&#x8FF0;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">status</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x8BF7;&#x6C42;&#x7ED3;&#x679C;&#x3002;</p>
        <ul>
          <li>Success&#xFF1A;&#x6210;&#x529F;&#x3002;</li>
          <li>Failed&#xFF1A;&#x5931;&#x8D25;&#x3002;</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

### 示例

**请求示例**

修改会议室8000。

```text
POST /api/v0.0.1/conference/update?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json
Content-Type:application/json; charset=utf-8
Host: 192.168.5.150

{
    "number":"8000",
    "participantepassword":"444444",
    "moderatorpassword":"555555",
    "waitformoderator":"yes"
}
```

**响应示例**

```text
HTTP/1.1 200 OK
Accept-Ranges: bytes
Connection: close
Content-Type: application/json
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

