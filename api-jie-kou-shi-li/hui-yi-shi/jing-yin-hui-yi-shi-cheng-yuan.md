---
description: 静音会议室的单个、多个成员。
---

# 静音会议室成员

### 请求地址

```text
POST /api/v0.0.1/conference/mute_member?token={token}&type={type}
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
      <td style="text-align:left">&#x4F1A;&#x8BAE;&#x5BA4;&#x53F7;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">membernumber</td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">Integer</td>
      <td style="text-align:left">
        <p>&#x6210;&#x5458;&#x53F7;&#x7801;&#x3002;</p>
        <p><b>&#x53D6;&#x503C;&#x8303;&#x56F4;</b>&#xFF1A;</p>
        <ul>
          <li>
            <p>&#x5355;&#x4E2A;&#x53F7;&#x7801;&#xFF1A;&#x9759;&#x97F3;&#x6307;&#x5B9A;&#x6210;&#x5458;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;membernumber&quot;:&quot;111&quot;</code>
            </p>
          </li>
          <li>
            <p>&#x591A;&#x4E2A;&#x53F7;&#x7801;&#xFF1A;&#x9759;&#x97F3;&#x591A;&#x4E2A;&#x6210;&#x5458;&#x3002;&#x591A;&#x4E2A;&#x53F7;&#x7801;&#x7528;&#x534A;&#x89D2;&#x9017;&#x53F7;&#xFF08;,&#xFF09;&#x9694;&#x5F00;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;membernumber&quot;:&quot;111,112&quot;</code>
            </p>
          </li>
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

静音会议室8000的成员-分机111。

```text
POST /api/v0.0.1/conference/mute_member?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150

{
    "number":"8000",
    "membernumber":"111"
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

