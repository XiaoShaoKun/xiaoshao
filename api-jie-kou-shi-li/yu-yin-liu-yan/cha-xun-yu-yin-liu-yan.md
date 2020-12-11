---
description: 查询分机的语音留言。
---

# 查询语音留言



### Endpoint

```text
POST /api/v0.0.1/voicemail/query?token={token}
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
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">
        <p>&#x8981;&#x67E5;&#x8BE2;&#x54EA;&#x4E2A;&#x5206;&#x673A;&#x7684;&#x8BED;&#x97F3;&#x7559;&#x8A00;&#x3002;</p>
        <ul>
          <li>
            <p><b>&#x67E5;&#x8BE2;&#x5355;&#x4E2A;&#x5206;&#x673A;</b>&#xFF1A;&#x8BBE;&#x7F6E; <code>extid</code> &#x4E3A;&#x5206;&#x673A;&#x53F7;&#x7801;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;extid&quot;:&quot;1000&quot;</code>
            </p>
          </li>
          <li>
            <p><b>&#x67E5;&#x8BE2;&#x591A;&#x4E2A;&#x5206;&#x673A;</b>&#xFF1A;&#x8BBE;&#x7F6E; <code>extid</code> &#x4E3A;&#x5206;&#x673A;&#x53F7;&#x7801;&#xFF0C;&#x591A;&#x4E2A;&#x5206;&#x673A;&#x4E4B;&#x95F4;&#x7528; <code>,</code> &#x9694;&#x5F00;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;extid&quot;: &quot;1000,1001&quot;</code>
            </p>
          </li>
          <li><b>&#x67E5;&#x8BE2;&#x6240;&#x6709;&#x5206;&#x673A;</b>&#xFF1A;&#x4E0D;&#x5E26; <code>extid</code> &#x8BF7;&#x6C42;&#x53C2;&#x6570;&#x3002;</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

### 响应参数

注： 如果查询的分机没有语音留言文件，PBX 只响应查询失败或者成功的参数。

| **名称** | **类型** | **描述** |
| :--- | :--- | :--- |
| `voicemails` | Object | Voicemails 对象参数。 |
| `extid` | String | 查询的分机号码。 |
| `voicemail` | Object | Voicemail 对象参数。 |
| `voicemailfile` | String | 语音留言文件名。 |
| `messagefrom` | String | 语音留言是哪个号码发送的。 |
| `voicemaildate` | String | 收到语音留言的时间。 |
| `voicemaillength` | String | 语音留言的时长。 |

### 实际示例

**请求示例**

查询分机102的语音留言。

```text
POST /api/v0.0.1/voicemail/query?token=813b621cfe8eecf445a2ce1f4a079ffe HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
    "extid": "102"
}
```

查询所有分机的语音留言。

```text
POST /api/v0.0.1/voicemail/query?token=813b621cfe8eecf445a2ce1f4a079ffe HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
```

**响应示例**

```text
HTTP/1.1 200 OK
Access-control-allow-origin: *
Access-control-allow-methods: GET, POST, OPTIONS, PUT, DELETE
{
    "status": "Success",
    "voicemails": [
        {
            "extid": "102",
            "voicemail": [
                {
                    "voicemailfile": "msg0000.wav",
                    "messagefrom": "6000",
                    "voicemaildate": "2020-04-07 10:56:40",
                    "voicemaillength": "4"
                },
                {
                    "voicemailfile": "msg0001.wav",
                    "messagefrom": "7001",
                    "voicemaildate": "2020-04-07 10:57:31",
                    "voicemaillength": "3"
                },
                {
                    "voicemailfile": "msg0002.wav",
                    "messagefrom": "7001",
                    "voicemaildate": "2020-04-07 11:00:08",
                    "voicemaillength": "2"
                }
            ]
        }
    ]
}
```

