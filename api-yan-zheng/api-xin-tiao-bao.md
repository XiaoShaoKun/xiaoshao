---
description: >-
  当连接 PBX 的第三方应用的 IP 地址、监听端口或者 URL 有变更的时候，可通过 API 的心跳包接口对 IP、Port 和 URL
  进行更新。当第三方应用和 API 没有交互的时候，可利用此接口定期发送请求从而更新 token 的有效时长，避免 token 在
  30分钟超时后被清除，造成事件不会上报以及请求失败。
---

# API 心跳包

注： 发送一次心跳包请求可使 token 的有效时长延长为30分钟。



### Endpoint

```text
POST /api/v0.0.1/heartbeat?token={token}
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
      <td style="text-align:left"><code>ipaddr</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x7B2C;&#x4E09;&#x65B9;&#x5E94;&#x7528;&#x53D8;&#x66F4;&#x540E;&#x7684;
        IP &#x5730;&#x5740;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>port</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x7B2C;&#x4E09;&#x65B9;&#x5E94;&#x7528;&#x53D8;&#x66F4;&#x540E;&#x7684;&#x76D1;&#x542C;&#x7AEF;&#x53E3;&#x3002;</td>
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
      <td style="text-align:left"><code>urltag</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x6307;&#x5B9A; URL &#x7684;&#x7C7B;&#x578B;&#xFF1A;</p>
        <ul>
          <li>
            <p>0&#xFF1A;&#x5B9A;&#x4E49;<code>url</code> &#x7684;&#x503C;&#x4E3A;&#x76F8;&#x5BF9;&#x8DEF;&#x5F84;&#x3002;PBX
              &#x4F1A;&#x5C06;&#x76F8;&#x5BF9;&#x8DEF;&#x5F84;&#x7684;<code>url</code>&#x4E0E;&#x7B2C;&#x4E09;&#x65B9;&#x670D;&#x52A1;&#x5668;
              IP &#x5730;&#x5740;&#x7ED3;&#x5408;&#x8D77;&#x6765;&#xFF0C;&#x53D1;&#x9001;
              API &#x62A5;&#x544A;&#x5230;&#x5177;&#x4F53;&#x7684;&#x8DEF;&#x5F84;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;&#x7B2C;&#x4E09;&#x65B9;&#x670D;&#x52A1;&#x5668;
              IP &#x5730;&#x5740;&#x4E3A;192.168.5.122&#xFF1B;&#x76D1;&#x542C;&#x7AEF;&#x53E3;&#x4E3A;8260&#xFF1B;<code>url</code>&#x8BBE;&#x7F6E;&#x4E3A;
              report&#xFF1B;&#x5219; PBX &#x53D1;&#x9001; API &#x62A5;&#x544A;&#x5230;192.168.5.122:8260/report
              &#x3002;</p>
          </li>
          <li>
            <p>1&#xFF1A;&#x5B9A;&#x4E49;<code>url</code>&#x7684;&#x503C;&#x4E3A;&#x7EDD;&#x5BF9;&#x8DEF;&#x5F84;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;&#x7B2C;&#x4E09;&#x65B9;&#x670D;&#x52A1;&#x5668;
              IP &#x5730;&#x5740;&#x4E3A;192.168.5.122&#xFF1B;<code>url</code> &#x8BBE;&#x7F6E;&#x4E3A;192.168.5.122:8260/report&#xFF1B;&#x5219;
              PBX &#x53D1;&#x9001; API &#x62A5;&#x544A;&#x5230;192.168.5.122:8260/report
              &#x3002;&#x6CE8;&#xFF1A; &#x4F7F;&#x7528;&#x7EDD;&#x5BF9;&#x8DEF;&#x5F84;&#xFF0C;&#x53EF;&#x4EE5;&#x907F;&#x514D;&#x590D;&#x6742;&#x7F51;&#x7EDC;&#x73AF;&#x5883;&#x4E0B;&#xFF0C;API
              &#x62A5;&#x544A;&#x65E0;&#x6CD5;&#x53D1;&#x9001;&#x6210;&#x529F;&#x7684;&#x95EE;&#x9898;&#x3002;</p>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

### 实际示例

**请求示例**第三方应用发送 API 心跳包对IP、Port 和 URL 进行更新。IP 地址变更为172.16.6.150，端口号变更为8280，URL 变更为172.16.6.150:8280/report。

```text
POST /api/v0.0.1/heartbeat?token=813b621cfe8eecf445a2ce1f4a079ffe HTTP/1.1 HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
    "ipaddr": "172.16.6.150",
    "port": "8280",
    "url": "172.16.6.150:8280",
    "urltag": "1"
}
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

