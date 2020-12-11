---
description: 查询 PBX 网页已创建的会议室配置详情。支持查询单个、多个或所有会议室。
---

# 查询会议室详情

### 请求地址

```text
POST /api/v0.0.1/conference/query?token={token}&type={type}
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
        <p>&#x56FA;&#x5B9A;&#x4F1A;&#x8BAE;&#x5BA4;&#x53F7;&#x7801;&#x3002;</p>
        <p><b>&#x53D6;&#x503C;&#x8303;&#x56F4;</b>&#xFF1A;</p>
        <ul>
          <li>
            <p>&#x5355;&#x4E2A;&#x4F1A;&#x8BAE;&#x5BA4;&#x53F7;&#x7801;&#xFF1A;&#x67E5;&#x8BE2;&#x6307;&#x5B9A;&#x4F1A;&#x8BAE;&#x5BA4;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;number&quot;:&quot;6500&quot;</code>
            </p>
          </li>
          <li>
            <p>&#x591A;&#x4E2A;&#x4F1A;&#x8BAE;&#x5BA4;&#x53F7;&#x7801;&#xFF1A;&#x67E5;&#x8BE2;&#x591A;&#x4E2A;&#x56FA;&#x5B9A;&#x4F1A;&#x8BAE;&#x5BA4;&#x3002;&#x591A;&#x4E2A;&#x4F1A;&#x8BAE;&#x5BA4;&#x53F7;&#x7801;&#x7528;&#x534A;&#x89D2;&#x9017;&#x53F7;&#xFF08;,&#xFF09;&#x9694;&#x5F00;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;number&quot;:&quot;6500,7500,8000&quot;</code>
            </p>
          </li>
          <li>all&#xFF1A;&#x67E5;&#x8BE2;&#x6240;&#x6709;&#x4F1A;&#x8BAE;&#x5BA4;&#x3002;</li>
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
    <tr>
      <td style="text-align:left">conferences</td>
      <td style="text-align:left">Array <a href="https://help.yeastar.com/zh-cn/s-series-developer-v2/api-v2/conference-query.html#conference-query__conferencesInfo">&lt;ConferenceInfo&gt;</a>
      </td>
      <td style="text-align:left">&#x4F1A;&#x8BAE;&#x5BA4;&#x4FE1;&#x606F;&#x5217;&#x8868;&#x3002;</td>
    </tr>
  </tbody>
</table>

ConferenceInfo

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
      <td style="text-align:left">number</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x4F1A;&#x8BAE;&#x5BA4;&#x53F7;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">name</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x4F1A;&#x8BAE;&#x5BA4;&#x540D;&#x79F0;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">participantepassword</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x4E0E;&#x4F1A;&#x8005;&#x5BC6;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">moderatorpassword</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x4E3B;&#x6301;&#x4EBA;&#x5BC6;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">waitformoderator</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x662F;&#x5426;&#x7B49;&#x5019;&#x4E3B;&#x6301;&#x4EBA;&#x8FDB;&#x5165;&#x540E;&#x624D;&#x5F00;&#x59CB;&#x4F1A;&#x8BAE;&#x3002;</p>
        <ul>
          <li>yes&#xFF1A;&#x662F;&#x3002;</li>
          <li>no&#xFF1A;&#x5426;&#x3002;</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

### 示例

**请求示例**

查询固定会议室6400的配置详情。

```text
POST /api/v0.0.1/conference/query?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150

{
	"number": "all"
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
    "status": "Success",
    "conferences": [
        {
            "number": "6500",
            "name": "6500",
            "participantepassword": "111111",
            "moderatorpassword": "222222",
            "waitformoderator": "no"
        },
        {
            "number": "7500",
            "name": "7500",
            "participantepassword": "",
            "moderatorpassword": "",
            "waitformoderator": "no"
        },
        {
            "number": "8000",
            "name": "testapi1",
            "participantepassword": "444444",
            "moderatorpassword": "555555",
            "waitformoderator": "no"
        }
    ]
}
```

