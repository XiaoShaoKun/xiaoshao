---
description: 查询单个、多个或所有正在进行的会议室信息。
---

# 查询正在进行的会议

### 请求地址

```text
POST /api/v0.0.1/conference/query_in_session?token={token}&type={type}
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
        <p>&#x4F1A;&#x8BDD;&#x4E2D;&#x7684;&#x4F1A;&#x8BAE;&#x5BA4;&#x53F7;&#x7801;&#x3002;</p>
        <p><b>&#x53D6;&#x503C;&#x8303;&#x56F4;</b>&#xFF1A;</p>
        <ul>
          <li>
            <p>&#x5355;&#x4E2A;&#x4F1A;&#x8BAE;&#x5BA4;&#x53F7;&#x7801;&#xFF1A;&#x67E5;&#x8BE2;&#x6307;&#x5B9A;&#x7684;&#x4F1A;&#x8BDD;&#x4E2D;&#x7684;&#x4F1A;&#x8BAE;&#x5BA4;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;number&quot;:&quot;8000&quot;</code>
            </p>
          </li>
          <li>
            <p>&#x591A;&#x4E2A;&#x4F1A;&#x8BAE;&#x5BA4;&#x53F7;&#x7801;&#xFF1A;&#x67E5;&#x8BE2;&#x591A;&#x4E2A;&#x4F1A;&#x8BDD;&#x4E2D;&#x7684;&#x4F1A;&#x8BAE;&#x5BA4;&#x3002;&#x591A;&#x4E2A;&#x4F1A;&#x8BAE;&#x5BA4;&#x53F7;&#x7801;&#x7528;&#x534A;&#x89D2;&#x9017;&#x53F7;&#xFF08;,&#xFF09;&#x9694;&#x5F00;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;number&quot;:&quot;6500,8000&quot;</code>
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
    <tr>
      <td style="text-align:left">conference</td>
      <td style="text-align:left">Array &lt;ConferenceInfo&gt;</td>
      <td style="text-align:left">&#x4F1A;&#x8BAE;&#x5BA4;&#x4FE1;&#x606F;&#x5217;&#x8868;&#x3002;</td>
    </tr>
  </tbody>
</table>

ConferenceInfo

| 参数 | 类型 | 描述 |
| :--- | :--- | :--- |
| callid | String | 每个通话的唯一 ID。 |
| conferencenumber | Integer | 会议室号码。 |
| conferencename | String | 会议室名称。 |
| members | Array &lt;MemberType&gt; | 与会成员信息。 |

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
      <td style="text-align:left">from</td>
      <td style="text-align:left">Integer</td>
      <td style="text-align:left">&#x4E3B;&#x53EB;&#x53F7;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">to</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x88AB;&#x53EB;&#x53F7;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">trunkname</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x901A;&#x8BDD;&#x4F7F;&#x7528;&#x7684;&#x4E2D;&#x7EE7;&#x540D;&#x79F0;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">channelid</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x901A;&#x8BDD;&#x4E2D;&#xFF0C;&#x6BCF;&#x4E2A;&#x6210;&#x5458;&#x7684;&#x901A;&#x8BDD;&#x901A;&#x9053;
        ID&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">memberstatus</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x4F1A;&#x8BAE;&#x5BA4;&#x6210;&#x5458;&#x7684;&#x72B6;&#x6001;&#x3002;</p>
        <ul>
          <li>Up&#xFF1A;&#x8BE5;&#x6210;&#x5458;&#x63A5;&#x53D7;&#x9080;&#x8BF7;&#xFF0C;&#x8FDB;&#x5165;&#x4F1A;&#x8BAE;&#x5BA4;&#x3002;</li>
          <li>HOLD&#xFF1A;&#x8BE5;&#x6210;&#x5458;&#x5DF2;&#x8FDB;&#x5165;&#x4F1A;&#x8BAE;&#x5BA4;&#xFF0C;&#x7B49;&#x5F85;&#x4E3B;&#x6301;&#x4EBA;&#x8FDB;&#x5165;&#x4F1A;&#x8BAE;&#x5BA4;&#x3002;</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

### 示例

**请求示例**

查询会话中的会议室8000的详细信息。

```text
POST /api/v0.0.1/conference/query_in_session?token=813b621cfe8eecf445a2ce1f4a079ffe
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150

{
	"number": "8000"
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
    "conference": [
        {
            "conferencenumber": "8000",
            "member": [
                {
                    "number": "111",
                    "channelid": "PJSIP/111-00000003",
                    "memberstatus": "Up"
                },
                {
                    "number": "114",
                    "channelid": "PJSIP/114-00000004",
                    "memberstatus": "Up"
                }
            ]
        }
    ]
}
```

