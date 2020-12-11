---
description: 通过本接口可以让分机向外线发起呼叫，从而使两者能够建立通话。（此接口只适用呼叫外线电话）。
---

# 拨打外线号码



### 条件

* 需通过呼出路由匹配呼出，所以该分机必须要有使用该呼出路由的权限。
* 发送分机拨打外线请求后，分机先响铃，摘机后，再拨打外线。如果开启了自动应答，则主叫方直接听到回铃音，被叫方响铃。

### Endpoint

```text
POST /api/v0.0.1/extension/dial_outbound?token={token}&type={type}
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
      <td style="text-align:left"><code>extid</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">&#x5206;&#x673A;&#x53F7;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>outto</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x8981;&#x62E8;&#x6253;&#x7684;&#x5916;&#x7EBF;&#x53F7;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>autoanswer</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x662F;&#x5426;&#x81EA;&#x52A8;&#x63A5;&#x542C;&#xFF08;&#x53EA;&#x9488;&#x5BF9;
          SIP &#x7EBF;&#x8DEF;&#x6709;&#x6548;&#xFF0C;&#x4E14;&#x9700;&#x8981;&#x8BDD;&#x673A;&#x652F;&#x6301;&#xFF0C;&#x6B64;&#x53C2;&#x6570;&#x4E0D;&#x5E26;&#x5219;&#x9ED8;&#x8BA4;&#x4E3A;&#x4E0D;&#x81EA;&#x52A8;&#x5E94;&#x7B54;&#xFF09;</p>
        <ul>
          <li>yes&#xFF1A;&#x662F;&#x3002;</li>
          <li>no&#xFF1A;&#x5426;&#x3002;</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

### 响应参数

| 名称 | 类型 | 描述 |
| :--- | :--- | :--- |


### 实际示例

**请求示例**

```text
POST /api/v0.0.1/extension/dial_outbound?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
	"extid":"101",
	"outto":"16103",
	"autoanswer":"no"
}
```

```text
POST /api/v0.0.1/extension/dial_outbound?token=813b621cfe8eecf445a2ce1f4a079ffe&type=xml HTTP/1.1
Content-Type:application/xml; charset=utf-8
Host: 172.16.6.150
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
	<extid>101</extid>
	<outto>16103</outto>
	<autoanswer>no</autoanswer>
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
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
    <status>Success</status>
</xml>

```

