---
description: 为指定分机设置闹铃。
---

# 添加闹铃

### 请求地址

```text
POST /api/v0.0.1/wakeupcall/create?token={token}&type={type}
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
      <td style="text-align:left">
        <p>&#x5206;&#x673A;&#x53F7;&#x7801;&#x3002;</p>
        <p><b>&#x53D6;&#x503C;&#x8303;&#x56F4;</b>&#xFF1A;</p>
        <ul>
          <li>
            <p>&#x5355;&#x4E2A;&#x5206;&#x673A;&#x53F7;&#x7801;&#xFF1A;&#x4E3A;&#x6307;&#x5B9A;&#x5206;&#x673A;&#x6DFB;&#x52A0;&#x95F9;&#x94C3;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;number&quot;:&quot;110&quot;</code>
            </p>
          </li>
          <li>
            <p>&#x591A;&#x4E2A;&#x5206;&#x673A;&#x53F7;&#x7801;&#xFF1A;&#x4E3A;&#x591A;&#x4E2A;&#x5206;&#x673A;&#x6DFB;&#x52A0;&#x540C;&#x4E00;&#x4E2A;&#x95F9;&#x94C3;&#x3002;&#x591A;&#x4E2A;&#x5206;&#x673A;&#x53F7;&#x7801;&#x7528;&#x534A;&#x89D2;&#x9017;&#x53F7;&#xFF08;,&#xFF09;&#x9694;&#x5F00;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;number&quot;:&quot;110,111&quot;</code>
            </p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">time</td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x95F9;&#x94C3;&#x65F6;&#x95F4;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">type</td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x95F9;&#x94C3;&#x7C7B;&#x578B;&#x3002;</p>
        <p><b>&#x53D6;&#x503C;&#x8303;&#x56F4;</b>&#xFF1A;</p>
        <ul>
          <li>
            <p>onetime&#xFF1A;&#x4E00;&#x6B21;&#x3002;</p>
            <p>&#x5F53;&#x95F9;&#x94C3;&#x5B8C;&#x6210;&#x8BBE;&#x7F6E;&#x7684;&#x91CD;&#x590D;&#x6B21;&#x6570;&#x4E4B;&#x540E;&#xFF0C;&#x8BE5;&#x6761;&#x95F9;&#x94C3;&#x5C06;&#x88AB;&#x81EA;&#x52A8;&#x5220;&#x9664;&#x3002;</p>
          </li>
          <li>
            <p>custom&#xFF1A;&#x81EA;&#x5B9A;&#x4E49;&#x3002;</p>
            <p><code>type</code> &#x4E3A; <code>custom</code> &#x65F6;&#xFF0C;<code>weekdays</code> &#x4E0D;&#x4E3A;&#x7A7A;&#x3002;</p>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">weekdays</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">Integer</td>
      <td style="text-align:left">
        <p>&#x95F9;&#x94C3;&#x9002;&#x7528;&#x7684;&#x661F;&#x671F;&#x3002;</p>
        <p><b>&#x53D6;&#x503C;&#x8303;&#x56F4;</b>&#xFF1A;0~6&#x3002;&#x5176;&#x4E2D;&#xFF0C;0&#x8868;&#x793A;&#x5468;&#x65E5;&#xFF0C;1-6&#x8868;&#x793A;&#x5468;&#x4E00;&#x5230;&#x5468;&#x516D;&#x3002;&#x6CE8;&#xFF1A;</p>
        <p><code>type</code> &#x4E3A; <code>custom</code> &#x65F6;&#xFF0C;&#x6B64;&#x9879;&#x4E0D;&#x4E3A;&#x7A7A;&#x3002;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">prompt</td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x95F9;&#x94C3;&#x63D0;&#x793A;&#x97F3;&#x3002;</p>
        <p>&#x6B64;&#x63D0;&#x793A;&#x97F3;&#x5FC5;&#x987B;&#x4E3A;&#x81EA;&#x5B9A;&#x4E49;&#x63D0;&#x793A;&#x97F3;&#x3002;</p>
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

为分机106添加闹铃。

```text
POST /api/v0.0.1/wakeupcall/create?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150

{
    "number":"106",
    "type":"custom",
    "time":"15:55",
    "weekdays":"0,1,2,3,5",
    "prompt":"custom/test"
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

