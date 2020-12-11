---
description: 查询单个 SIP 中继、多个 SIP 中继 或所有 SIP 中继的基本设置。
---

# 查询 SIP 中继



### Endpoint

```text
POST /api/v1.1.0/siptrunk/query?token={token}&type={type}
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
      <td style="text-align:left"><code>trunkname</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>SIP &#x4E2D;&#x7EE7;&#x7684;&#x540D;&#x79F0;&#x3002;</p>
        <ul>
          <li>
            <p><b>&#x67E5;&#x8BE2;&#x5355;&#x4E2A; SIP &#x4E2D;&#x7EE7;</b>&#xFF1A;&#x8BBE;&#x7F6E; <code>trunkname</code> &#x4E3A;
              SIP &#x4E2D;&#x7EE7;&#x7684;&#x540D;&#x79F0;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;trunkname&quot;:&quot;SIP&quot;</code>
            </p>
          </li>
          <li>
            <p><b>&#x67E5;&#x8BE2;&#x591A;&#x4E2A; SIP &#x4E2D;&#x7EE7;</b>&#xFF1A;&#x8BBE;&#x7F6E; <code>trunkname</code> &#x4E3A;
              SIP &#x4E2D;&#x7EE7;&#x7684;&#x540D;&#x79F0;&#xFF0C;&#x591A;&#x4E2A; SIP
              &#x4E2D;&#x7EE7;&#x4E4B;&#x95F4;&#x7528; <code>,</code> &#x9694;&#x5F00;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;trunkname&quot;: &quot;SIP1,SIP2&quot;</code>
            </p>
          </li>
          <li><b>&#x67E5;&#x8BE2;&#x6240;&#x6709; SIP &#x4E2D;&#x7EE7;</b>&#xFF1A;&#x8BBE;&#x7F6E; <code>trunkname</code>&#x4E3A;<code>all</code>&#x3002;</li>
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
      <td style="text-align:left"><code>trunks</code>
      </td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left">&#x5BF9;&#x8C61;&#x53C2;&#x6570;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>id</code>
      </td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">&#x4E2D;&#x7EE7;&#x7684;&#x6807;&#x8BC6;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>trunkname</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x4E2D;&#x7EE7;&#x540D;&#x79F0;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>trunktype</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x4E2D;&#x7EE7;&#x7C7B;&#x578B;&#x3002;</p>
        <ul>
          <li>register&#xFF1A;&#x6CE8;&#x518C;&#x4E2D;&#x7EE7;&#x3002;</li>
          <li>peer&#xFF1A;&#x70B9;&#x5BF9;&#x70B9;&#x4E2D;&#x7EE7;&#x3002;</li>
          <li>account&#xFF1A;&#x8D26;&#x53F7;&#x4E2D;&#x7EE7;&#x3002;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&#x6CE8;&#x518C;&#x4E2D;&#x7EE7;</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>host</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">SIP &#x8FD0;&#x8425;&#x5546;&#x7684;&#x57DF;&#x540D;&#x6216; IP &#x5730;&#x5740;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>port</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x4E2D;&#x7EE7;&#x7684; SIP &#x7AEF;&#x53E3;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>domain</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">SIP &#x8FD0;&#x8425;&#x5546;&#x7684;&#x57DF;&#x540D;&#x6216; IP &#x5730;&#x5740;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>username</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">SIP &#x8FD0;&#x8425;&#x5546;&#x63D0;&#x4F9B;&#x7684; SIP &#x8D26;&#x53F7;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>authname</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">SIP &#x8FD0;&#x8425;&#x5546;&#x63D0;&#x4F9B;&#x7684; SIP &#x8D26;&#x53F7;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>fromuser</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">From &#x5934;&#x57DF;&#x3002;&#x6CE8;&#xFF1A; &#x5982;&#x679C; SIP &#x8FD0;&#x8425;&#x5546;&#x4E0D;&#x652F;&#x6301;&#xFF0C;&#x5219;&#x653E;&#x7A7A;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>password</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">SIP &#x8D26;&#x53F7;&#x7684;&#x5BC6;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x70B9;&#x5BF9;&#x70B9;&#x4E2D;&#x7EE7;</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>host</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">SIP &#x8FD0;&#x8425;&#x5546;&#x7684;&#x57DF;&#x540D;&#x6216; IP &#x5730;&#x5740;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>port</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x4E2D;&#x7EE7;&#x7684; SIP &#x7AEF;&#x53E3;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>domain</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">SIP &#x8FD0;&#x8425;&#x5546;&#x7684;&#x57DF;&#x540D;&#x6216; IP &#x5730;&#x5740;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x8D26;&#x53F7;&#x4E2D;&#x7EE7;</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>username</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x8D26;&#x53F7;&#x4E2D;&#x7EE7;&#x7684;&#x7528;&#x6237;&#x540D;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>authname</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x8D26;&#x53F7;&#x4E2D;&#x7EE7;&#x7684;&#x8BA4;&#x8BC1;&#x540D;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>password</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x8D26;&#x53F7;&#x4E2D;&#x7EE7;&#x7684;&#x5BC6;&#x7801;&#x3002;</td>
    </tr>
  </tbody>
</table>

### 实际示例

**请求示例**

```text
POST /api/v0.0.1/siptrunk/query?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
    "trunkname": "all"
}
```

```text
POST /api/v0.0.1/siptrunk/query?token=813b621cfe8eecf445a2ce1f4a079ffe&type=xml HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
	<trunkname>all</trunkname>
</xml>
```

**响应示例**

```text
HTTP/1.1 200 OK
Access-control-allow-origin: *
Access-control-allow-methods: GET, POST, OPTIONS, PUT, DELETE
{
    "status": "Success",
    "trunks": [
        {
            "id": "1",
            "trunkname": "to-108-16",
            "tech": "pjsip",
            "trunktype": "register",
            "host": "172.16.108.16",
            "port": "5060",
            "domain": "172.16.108.16",
            "username": "6100",
            "authname": "6100",
            "fromuser": "",
            "password": "@123456wW"
        },
        {
            "id": "2",
            "trunkname": "to-18-16-2",
            "tech": "pjsip",
            "trunktype": "peer",
            "host": "172.16.108.16",
            "port": "5060",
            "domain": "172.16.108.16"
        }
    ]
}
```

```text
HTTP/1.1 200 OK
Access-control-allow-origin: *
Access-control-allow-methods: GET, POST, OPTIONS, PUT, DELETE
<?xml version="1.0" encoding="utf-8"?>
<xml>
    <status>Success</status>
    <trunks>
        <item id="0">
            <id>2</id>
            <trunkname>to-18-16-2</trunkname>
            <tech>pjsip</tech>
            <trunktype>peer</trunktype>
            <host>172.16.108.16</host>
            <port>5060</port>
            <domain>172.16.108.16</domain>
        </item>
    </trunks>
</xml>
```

