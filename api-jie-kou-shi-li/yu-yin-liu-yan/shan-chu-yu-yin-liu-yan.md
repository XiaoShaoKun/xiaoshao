---
description: 删除分机的语音留言。
---

# 删除语音留言



### Endpoint

```text
POST /api/v0.0.1/voicemail/delete?token={token}
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
      <td style="text-align:left">&#x8981;&#x5220;&#x9664;&#x54EA;&#x4E2A;&#x5206;&#x673A;&#x7684;&#x8BED;&#x97F3;&#x7559;&#x8A00;&#x6587;&#x4EF6;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>voicemailfile</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x8BED;&#x97F3;&#x7559;&#x8A00;&#x6587;&#x4EF6;&#x540D;&#x3002;</p>
        <ul>
          <li>&#x586B;&#x5199;&#x5177;&#x4F53;&#x8BED;&#x97F3;&#x7559;&#x8A00;&#x7684;&#x540D;&#x79F0;&#xFF0C;&#x5220;&#x9664;&#x6307;&#x5B9A;&#x7684;&#x8BED;&#x97F3;&#x7559;&#x8A00;&#x6587;&#x4EF6;&#x3002;</li>
          <li>all&#xFF1A;&#x5220;&#x9664;&#x6307;&#x5B9A;&#x8BED;&#x97F3;&#x7559;&#x8A00;&#x72B6;&#x6001;&#x7684;&#x6240;&#x6709;&#x7684;&#x8BED;&#x97F3;&#x7559;&#x8A00;&#x6587;&#x4EF6;&#x3002;</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

### 实际示例

**请求示例**

```text
POST /api/v0.0.1/voicemail/delete?token=813b621cfe8eecf445a2ce1f4a079ffe HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
    "extid": "102",
    "voicemailfile": "msg0000.wav",
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

