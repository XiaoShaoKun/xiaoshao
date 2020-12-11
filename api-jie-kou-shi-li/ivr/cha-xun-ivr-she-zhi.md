---
description: 查询单个或多个 IVR 的详细信息，如：IVR 号码、名称、按键事件、响应超时时间。
---

# 查询 IVR 设置



### Endpoint

```text
POST /api/v0.0.1/ivr/query?token={token}&type={type}
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
      <td style="text-align:left"><code>name</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>IVR&#x53F7;&#x7801;&#x3002;</p>
        <ul>
          <li>
            <p><b>&#x67E5;&#x8BE2;&#x5355;&#x4E2A; IVR</b>&#xFF1A;&#x8BBE;&#x7F6E; <code>ivrid</code> &#x4E3A;
              IVR &#x53F7;&#x7801;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;name&quot;:&quot;6500&quot;</code>
            </p>
          </li>
          <li>
            <p><b>&#x67E5;&#x8BE2;&#x591A;&#x4E2A; IVR</b>&#xFF1A;&#x8BBE;&#x7F6E; <code>ivrid</code> &#x4E3A;
              IVR &#x53F7;&#x7801;&#xFF0C;&#x591A;&#x4E2A; IVR&#x4E4B;&#x95F4;&#x7528; <code>,</code> &#x9694;&#x5F00;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;name&quot;:&quot;6500,6501,6502&quot;</code>
            </p>
          </li>
          <li><b>&#x67E5;&#x8BE2;&#x6240;&#x6709; IVR</b>&#xFF1A;&#x4E0D;&#x5E26; <code>name</code> &#x8BF7;&#x6C42;&#x53C2;&#x6570;&#x3002;</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

### 响应参数

| 名称 | 类型 | 描述 |
| :--- | :--- | :--- |
| `ivrname` | String | IVR 名称。 |
| `prompt` | String | IVR 提示音。 |
| `promptrepeat` | String | 提示音播放次数。 |
| `responsetimeout` | Int | 响应超时时间。 |

### 实际示例

**请求示例**

查询 IVR 名称为test\_ivr。

```text
POST /api/v0.0.1/ivr/query?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
    "name": "test_ivr"
}
```

```text
POST /api/v0.0.1/ivr/query?token=813b621cfe8eecf445a2ce1f4a079ffe&type=xml HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
	<name>test_ivr</name>
</xml>
```

查询所有IVR。

```text
POST /api/v0.0.1/ivr/query?token=813b621cfe8eecf445a2ce1f4a079ffe HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 192.168.5.150
```

**响应示例**

```text
HTTP/1.1 200 OK
Access-control-allow-origin: *
Access-control-allow-methods: GET, POST, OPTIONS, PUT, DELETE
{
    "status": "Success",
    "ivr": [
        {
            "ivrid": "4",
            "promptrepeat": "3",
            "responsetimeout": "5",
            "ivrname": "test_ivr",
            "prompt": "haruhi3"
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
	<ivr>
		<item id="0">
			<ivrid>4</ivrid>
			<promptrepeat>3</promptrepeat>
			<responsetimeout>5</responsetimeout>
			<ivrname>test_ivr</ivrname>
			<prompt>haruhi3</prompt>
		</item>
	</ivr>
</xml>
```

