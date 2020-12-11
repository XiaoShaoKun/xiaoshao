---
description: 删除指定分机的闹铃。
---

# 删除闹铃

### 请求地址

```text
POST /api/v0.0.1/wakeupcall/delete?token={token}&type={type}
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
      <td style="text-align:left">wakeupid</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">Integer</td>
      <td style="text-align:left">
        <p>&#x95F9;&#x94C3;&#x7684;&#x552F;&#x4E00; ID&#x3002;&#x4E0D;&#x5E26;&#x6B64;&#x53C2;&#x6570;&#xFF0C;&#x8868;&#x793A;&#x5220;&#x9664;&#x6307;&#x5B9A;&#x5206;&#x673A;&#x7684;&#x6240;&#x6709;&#x95F9;&#x94C3;&#x3002;</p>
        <p><b>&#x53D6;&#x503C;&#x8303;&#x56F4;</b>&#xFF1A;</p>
        <ul>
          <li>
            <p>&#x5355;&#x4E2A;&#x95F9;&#x94C3; ID&#xFF1A;&#x5220;&#x9664;&#x6307;&#x5B9A;&#x5206;&#x673A;&#x7684;&#x6307;&#x5B9A;&#x95F9;&#x94C3;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;wakeupid&quot;:&quot;8&quot;</code>
            </p>
          </li>
          <li>
            <p>&#x591A;&#x4E2A;&#x95F9;&#x94C3; ID&#xFF1A;&#x5220;&#x9664;&#x6307;&#x5B9A;&#x5206;&#x673A;&#x7684;&#x591A;&#x4E2A;&#x95F9;&#x94C3;&#x3002;&#x591A;&#x4E2A;&#x95F9;&#x94C3;
              ID &#x7528;&#x534A;&#x89D2;&#x9017;&#x53F7;&#xFF08;,&#xFF09;&#x9694;&#x5F00;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;wakeupid&quot;: &quot;8,9&quot;</code>
            </p>
          </li>
          <li>
            <p>all&#xFF1A;&#x5220;&#x9664;&#x6307;&#x5B9A;&#x5206;&#x673A;&#x7684;&#x6240;&#x6709;&#x95F9;&#x94C3;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;wakeupid&quot;: &quot;all&quot;</code>
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

删除分机106的闹铃。

```text
POST /api/v2.0.0/wakeupcall/delete?token=1e3b3ebb6a974cb42ed31de5413df52d
Content-Type:application/json; charset=utf-8
Host: 192.168.5.150

{
    "wakeupid":"106"
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

