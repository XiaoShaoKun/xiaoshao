---
description: 更改广播组的设置。
---

# 编辑广播组

### 请求地址

```text
POST /api/v0.0.1/paginggroup/update?token={token}
```

### 请求参数

根据不同类型的广播组，需要发送不同的请求参数。

* 单向传呼
* 双向对讲

单向传呼

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
      <td style="text-align:left">&#x5E7F;&#x64AD;&#x7EC4;&#x53F7;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">name</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x5E7F;&#x64AD;&#x7EC4;&#x540D;&#x79F0;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">type</td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x5E7F;&#x64AD;&#x7EC4;&#x7C7B;&#x578B;&#x3002;</p>
        <p><b>&#x53D6;&#x503C;</b>&#xFF1A;</p>
        <p>paging&#xFF1A;&#x5355;&#x5411;&#x4F20;&#x547C;&#x3002;&#x5E7F;&#x64AD;&#x7EC4;&#x5185;&#x7684;&#x5206;&#x673A;&#x53EA;&#x80FD;&#x542C;&#x5230;&#x53D1;&#x8D77;&#x8005;&#x7684;&#x58F0;&#x97F3;&#x3002;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">member</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x5E7F;&#x64AD;&#x7EC4;&#x6210;&#x5458;&#x3002;</p>
        <p><b>&#x53D6;&#x503C;</b>&#xFF1A;&#x9009;&#x62E9;&#x5206;&#x673A;&#x4E3A;&#x5E7F;&#x64AD;&#x7EC4;&#x6210;&#x5458;&#x3002;&#x591A;&#x4E2A;&#x5206;&#x673A;&#x7528;&#x534A;&#x89D2;&#x9017;&#x53F7;&#xFF08;,&#xFF09;&#x9694;&#x5F00;&#x3002;</p>
        <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;member&quot;:&quot;1000,1001,1002&quot;</code>&#x3002;</p>
      </td>
    </tr>
  </tbody>
</table>

双向对讲

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
      <td style="text-align:left">&#x5E7F;&#x64AD;&#x7EC4;&#x53F7;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">name</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x5E7F;&#x64AD;&#x7EC4;&#x540D;&#x79F0;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">type</td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x5E7F;&#x64AD;&#x7EC4;&#x7C7B;&#x578B;&#x3002;</p>
        <p><b>&#x53D6;&#x503C;</b>&#xFF1A;</p>
        <p>intercom&#xFF1A;&#x53CC;&#x5411;&#x5BF9;&#x8BB2;&#x3002;&#x5E7F;&#x64AD;&#x7EC4;&#x5185;&#x7684;&#x6240;&#x6709;&#x5206;&#x673A;&#x90FD;&#x53EF;&#x4EE5;&#x8FDB;&#x884C;&#x901A;&#x8BDD;&#x5E76;&#x4E14;&#x90FD;&#x80FD;&#x542C;&#x89C1;&#x5F7C;&#x6B64;&#x7684;&#x58F0;&#x97F3;&#x3002;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">member</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x5E7F;&#x64AD;&#x7EC4;&#x6210;&#x5458;&#x3002;</p>
        <p><b>&#x53D6;&#x503C;</b>&#xFF1A;&#x9009;&#x62E9;&#x5206;&#x673A;&#x4E3A;&#x5E7F;&#x64AD;&#x7EC4;&#x6210;&#x5458;&#x3002;&#x591A;&#x4E2A;&#x5206;&#x673A;&#x7528;&#x534A;&#x89D2;&#x9017;&#x53F7;&#xFF08;,&#xFF09;&#x9694;&#x5F00;&#x3002;</p>
        <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;member&quot;:&quot;1000,1001,1002&quot;</code>&#x3002;</p>
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

```text
POST /api/v0.0.1/paginggroup/update?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150

{
    "number":"8891",
    "name":"test_api_paging_10",
    "type":"intercom",
    "member":"106,108"
}
```

**响应示例**

```text
HTTP/1.1 200 OK
Server: Boa/0.94.14rc21
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

