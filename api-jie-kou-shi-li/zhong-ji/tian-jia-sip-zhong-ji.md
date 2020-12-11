---
description: 添加并设置 SIP 中继。
---

# 添加 SIP 中继



### Endpoint

```text
POST /api/v0.0.1/siptrunk/add?token={token}&type={type}
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
      <td style="text-align:left">&#x4E2D;&#x7EE7;&#x540D;&#x79F0;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>trunktype</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
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
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>host</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">SIP &#x8FD0;&#x8425;&#x5546;&#x7684;&#x57DF;&#x540D;&#x6216; IP &#x5730;&#x5740;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>port</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x4E2D;&#x7EE7;&#x7684; SIP &#x7AEF;&#x53E3;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>username</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">SIP &#x8FD0;&#x8425;&#x5546;&#x63D0;&#x4F9B;&#x7684; SIP &#x8D26;&#x53F7;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>authname</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">SIP &#x8FD0;&#x8425;&#x5546;&#x63D0;&#x4F9B;&#x7684; SIP &#x8D26;&#x53F7;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>fromuser</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">From &#x5934;&#x57DF;&#x3002;&#x6CE8;&#xFF1A; &#x5982;&#x679C; SIP &#x8FD0;&#x8425;&#x5546;&#x4E0D;&#x652F;&#x6301;&#xFF0C;&#x5219;&#x653E;&#x7A7A;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>password</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">SIP &#x8D26;&#x53F7;&#x7684;&#x5BC6;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x70B9;&#x5BF9;&#x70B9;&#x4E2D;&#x7EE7;</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>host</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">SIP &#x8FD0;&#x8425;&#x5546;&#x7684;&#x57DF;&#x540D;&#x6216; IP &#x5730;&#x5740;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>port</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x4E2D;&#x7EE7;&#x7684; SIP &#x7AEF;&#x53E3;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x8D26;&#x53F7;&#x4E2D;&#x7EE7;</td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left"><code>username</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x8D26;&#x53F7;&#x4E2D;&#x7EE7;&#x7684;&#x7528;&#x6237;&#x540D;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>authname</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x8D26;&#x53F7;&#x4E2D;&#x7EE7;&#x7684;&#x8BA4;&#x8BC1;&#x540D;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>password</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x8D26;&#x53F7;&#x4E2D;&#x7EE7;&#x7684;&#x5BC6;&#x7801;&#x3002;</td>
    </tr>
  </tbody>
</table>

### 实际示例

**请求示例**

```text
POST /api/v0.0.1/siptrunk/add?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
    "trunkname": "to-108-16-test",
    "trunktype": "register",
    "host": "172.16.108.16",
    "port": "5060",
    "username":"6100",
    "authname":"6100",
    "password":"Rqzswb55"
}
```

```text
POST /api/v0.0.1/siptrunk/add?token=813b621cfe8eecf445a2ce1f4a079ffe&type=xml HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
	<trunkname>to-108-16-test</trunkname>
	<trunktype>register</trunktype>
	<host>172.16.108.16</host>
	<port>5060</port>
	<domain>172.16.108.16</domain>
	<username>6100</username>
	<authname>6100</authname>
	<password>Rqzswb55</password>
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



