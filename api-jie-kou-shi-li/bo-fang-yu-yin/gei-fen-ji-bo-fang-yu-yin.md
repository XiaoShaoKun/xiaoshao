---
description: 通过本接口可给内部分机播放语音，PBX 拨打分机，分机响铃接起后，听到提示音。
---

# 给分机播放语音



### Endpoint

```text
POST /api/v0.0.1/extension/playprompt?token={token}
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
      <td style="text-align:left"><code>prompt</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x8BED;&#x97F3;&#x6587;&#x4EF6;&#x540D;&#x79F0;&#x3002;&#x6CE8;&#xFF1A;</p>
        <ul>
          <li>&#x6587;&#x4EF6;&#x540D;&#x65E0;&#x9700;&#x52A0;&#x6587;&#x4EF6;&#x540E;&#x7F00;&#x3002;</li>
          <li>&#x6587;&#x4EF6;&#x540D;&#x5FC5;&#x987B;&#x5305;&#x542B;&#x5B57;&#x6BCD;&#xFF0C;&#x4E14;&#x4E0D;&#x80FD;&#x5E26;<code>+</code>&#x3002;</li>
          <li>&#x5FC5;&#x987B;&#x5C06;&#x8BED;&#x97F3;&#x6587;&#x4EF6;&#x4E0A;&#x4F20;&#x5230;
            System Recordings&#x9875;&#x9762;&#x3002;</li>
        </ul>
        <p>&#x591A;&#x4E2A;&#x8BED;&#x97F3;&#x6587;&#x4EF6;&#x4E4B;&#x95F4;&#x7528;<code>+</code>&#x8FDE;&#x63A5;&#x3002;&#x4F8B;&#x5982;&#xFF1A;<code>&quot;prompt:music1+music2&quot;</code>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>autoanswer</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x662F;&#x5426;&#x81EA;&#x52A8;&#x63A5;&#x542C;&#x3002;</p>
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
| `callid` | String | 该通通话的 id。 |

### 实际示例

**请求示例**

播放一个语音文件。

```text
POST /api/v0.0.1/extension/playprompt?token=813b621cfe8eecf445a2ce1f4a079ffe HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
	"extid":"101",
	"prompt":"haruhi3",
	"autoanswer":"no"
}
```

播放多个语音文件。

```text
POST /api/v0.0.1/extension/playprompt?token=813b621cfe8eecf445a2ce1f4a079ffe HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
	"extid":"101",
	"prompt":"haruhi3+xiaoshao5",
	"autoanswer":"no"
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

