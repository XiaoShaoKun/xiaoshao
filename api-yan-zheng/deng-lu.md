---
description: IPPBX API 采用用户名和密码的方式验证，只有用户名和密码验证通过的应用服务器，API 才会处理其发送的请求。
---

# 登陆



 注：

* 你需要先将 API 的密码通过 MD5 加密，获取32位小写密码。使用加密过的密码进行 API 验证。
* 如果密码连续错误五次，则该第三方应用的 IP 将会被锁10分钟。



### Endpoint

```text
POST /api/v0.0.1/login?type={type}
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
      <td style="text-align:left"><code>username</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x5728; PBX &#x4E8C;&#x6B21;&#x5F00;&#x53D1;&#x63A5;&#x53E3;&#x754C;&#x9762;&#x8BBE;&#x7F6E;&#x7684;&#x7528;&#x6237;&#x540D;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>password</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x5C06; PBX &#x4E8C;&#x6B21;&#x5F00;&#x53D1;&#x63A5;&#x53E3;&#x754C;&#x9762;&#x8BBE;&#x7F6E;&#x7684;&#x5BC6;&#x7801;&#x901A;&#x8FC7;
          MD5 &#x52A0;&#x5BC6;&#x3002;</p>
        <p>&#x586B;&#x5199;&#x52A0;&#x5BC6;&#x540E;&#x7684;32&#x4F4D;&#x5C0F;&#x5199;&#x5BC6;&#x7801;&#x3002;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>port</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x7AEF;&#x53E3;&#x53F7;&#xFF0C;&#x6B64;&#x7AEF;&#x53E3;&#x53F7;&#x4E3A;&#x7B2C;&#x4E09;&#x65B9;&#x5E94;&#x7528;&#x7528;&#x4E8E;&#x76D1;&#x542C;
        API &#x53D1;&#x9001;&#x7684;&#x4E8B;&#x4EF6;&#x62A5;&#x544A;&#x7684;&#x7AEF;&#x53E3;&#x53F7;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>url</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x7B2C;&#x4E09;&#x65B9;&#x5E94;&#x7528;&#x670D;&#x52A1;&#x5668;&#x83B7;&#x53D6;
        API &#x62A5;&#x544A;&#x7684; URL&#x3002;&#x6CE8;&#xFF1A; &#x5982;&#x679C;&#x4E0D;&#x5E26;&#x6B64;&#x53C2;&#x6570;&#xFF0C;&#x5219;
        PBX &#x9ED8;&#x8BA4;&#x5411;&#x7B2C;&#x4E09;&#x65B9;&#x5E94;&#x7528;&#x670D;&#x52A1;&#x5668;&#x7684;
        IP &#x5730;&#x5740;&#x53D1;&#x9001; API &#x62A5;&#x544A;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>version</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x53D1;&#x9001; API &#x4E8B;&#x4EF6;&#x62A5;&#x544A;&#x683C;&#x5F0F;&#x7684;&#x7248;&#x672C;&#x3002;&#x6CE8;&#xFF1A;
        &#x8BBE;&#x7F6E;<code>&quot;version&quot;:&quot;1.0.2&quot;</code>&#x53EF;&#x4EE5;&#x4FEE;&#x590D;
        API &#x4E8B;&#x4EF6;&#x62A5;&#x544A;&#x7684;&#x8BED;&#x53E5;&#x4E0D;&#x7B26;&#x5408;
        JSON &#x683C;&#x5F0F;&#x7684;&#x95EE;&#x9898;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>urltag</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x6307;&#x5B9A; URL &#x7684;&#x7C7B;&#x578B;&#xFF1A;</p>
        <ul>
          <li>
            <p>0&#xFF1A;&#x5B9A;&#x4E49;<code>url</code>&#x7684;&#x503C;&#x4E3A;&#x76F8;&#x5BF9;&#x8DEF;&#x5F84;&#x3002;PBX
              &#x4F1A;&#x5C06;&#x76F8;&#x5BF9;&#x8DEF;&#x5F84;&#x7684; <code>url</code> &#x4E0E;&#x7B2C;&#x4E09;&#x65B9;&#x670D;&#x52A1;&#x5668;
              IP &#x5730;&#x5740;&#x7ED3;&#x5408;&#x8D77;&#x6765;&#xFF0C;&#x53D1;&#x9001;
              API &#x62A5;&#x544A;&#x5230;&#x5177;&#x4F53;&#x7684;&#x8DEF;&#x5F84;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;&#x7B2C;&#x4E09;&#x65B9;&#x670D;&#x52A1;&#x5668;
              IP &#x5730;&#x5740;&#x4E3A;110.22.2.3&#xFF1B;&#x76D1;&#x542C;&#x7AEF;&#x53E3;&#x4E3A;8260&#xFF1B;<code>url</code>&#x8BBE;&#x7F6E;&#x4E3A;
              report&#xFF1B;&#x5219; PBX &#x53D1;&#x9001; API &#x62A5;&#x544A;&#x5230;110.22.2.3:8260/report
              &#x3002;</p>
          </li>
          <li>
            <p>1&#xFF1A;&#x5B9A;&#x4E49;<code>url</code> &#x7684;&#x503C;&#x4E3A;&#x7EDD;&#x5BF9;&#x8DEF;&#x5F84;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;&#x7B2C;&#x4E09;&#x65B9;&#x670D;&#x52A1;&#x5668;
              IP &#x5730;&#x5740;&#x4E3A;110.22.2.3&#xFF1B;<code>url</code> &#x8BBE;&#x7F6E;&#x4E3A;110.22.2.3:8260/report&#xFF1B;&#x5219;
              PBX &#x53D1;&#x9001; API &#x62A5;&#x544A;&#x5230;110.22.2.3:8260/report
              &#x3002;&#x6CE8;&#xFF1A; &#x4F7F;&#x7528;&#x7EDD;&#x5BF9;&#x8DEF;&#x5F84;&#xFF0C;&#x53EF;&#x4EE5;&#x907F;&#x514D;&#x590D;&#x6742;&#x7F51;&#x7EDC;&#x73AF;&#x5883;&#x4E0B;&#xFF0C;API
              &#x62A5;&#x544A;&#x65E0;&#x6CD5;&#x53D1;&#x9001;&#x6210;&#x529F;&#x7684;&#x95EE;&#x9898;&#x3002;</p>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

### 响应参数

| 名称 | 类型 | 描述 |
| :--- | :--- | :--- |
| `token` | String | 调用接口凭证，所有的 API 请求都需用到该 token。 |

注：

* API `token` 是第三方应用成功连接 PBX 后生成的。所有的 API 请求都需要带上 API 验证时所返回的token。
* token 有效时长为30分钟。

  30分钟内如果 API 和第三方应用没有任何交互（如：第三方应用发送 API 请求），则该 token 将被 IPPBX 系统清除。可通过心跳包接口延长 token 的有效时长，每发送一次心跳包可使 token 的有效时长延长为30分钟。

### 实际示例

**请求示例**

```text
POST /api/v1.1.0/login?type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.101.37
{
    "username": "xiaoshao",
    "password": "e10adc3949ba59abbe56e057f20f883e",
    "port": "8260",
    "version": "0.0.1",
    "url": "172.16.6.150:8260",
    "urltag": 1
}
```



```text
POST /api/v1.1.0/login?type=xml HTTP/1.1
Content-Type:application/xml; charset=utf-8
Host: 172.16.101.37
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
	<username>api</username>
	<password>e10adc3949ba59abbe56e057f20f883e</password>
	<port>8260</port>
	<version>0.0.1</version>
	<url>172.16.6.150:8260</url>
	<urltag>1</urltag>
</xml>
```

**响应示例**

第三方应用服务器登录成功。

```text
HTTP/1.1 200 OK
Access-control-allow-origin: *
Access-control-allow-methods: GET, POST, OPTIONS, PUT, DELETE
{
    "status": "Success",
    "token": "813b621cfe8eecf445a2ce1f4a079ffe"
}
```

第三方应用服务器登录失败。

```text
HTTP/1.1 200 OK
Access-control-allow-origin: *
Access-control-allow-methods: GET, POST, OPTIONS, PUT, DELETE
{
      "status": "Failed", 
      "errno": "30003"
}
```

