---
description: 下载分机的语音留言文件。
---

# 下载语音留言

### Endpoint

```text
POST /api/v0.0.1/voicemail/get_random?token={token}
```

### 请求参数

注： 要下载分机的某个语音留言文件，需要先向 PBX 请求该语音留言文件的随机串。

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
      <td style="text-align:left">&#x8981;&#x4E0B;&#x8F7D;&#x54EA;&#x4E2A;&#x5206;&#x673A;&#x7684;&#x8BED;&#x97F3;&#x7559;&#x8A00;&#x6587;&#x4EF6;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>voicemailfile</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x8BED;&#x97F3;&#x7559;&#x8A00;&#x6587;&#x4EF6;&#x540D;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>allowedip</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x8BBE;&#x7F6E;&#x5141;&#x8BB8;&#x4E0B;&#x8F7D;&#x8BED;&#x97F3;&#x7559;&#x8A00;&#x7684;&#x8BBE;&#x5907;
          IP &#x5730;&#x5740;&#x3002;</p>
        <ul>
          <li>&#x4E0D;&#x586B;&#x5199;<code>allowedip</code>&#xFF1A;&#x53EA;&#x80FD;&#x901A;&#x8FC7;&#x7B2C;&#x4E09;&#x65B9;&#x670D;&#x52A1;&#x5668;&#x53EF;&#x4EE5;&#x4E0B;&#x8F7D;&#x6587;&#x4EF6;&#x3002;</li>
          <li><code>allowedip</code> &#x503C;&#x4E3A;&#x7A7A;&#xFF1A;&#x53EA;&#x80FD;&#x901A;&#x8FC7;&#x7B2C;&#x4E09;&#x65B9;&#x670D;&#x52A1;&#x5668;&#x53EF;&#x4EE5;&#x4E0B;&#x8F7D;&#x6587;&#x4EF6;&#x3002;</li>
          <li><code>allowedip</code> &#x586B;&#x5199; IP &#x5730;&#x5740;&#xFF1A;&#x53EA;&#x80FD;&#x901A;&#x8FC7;&#x8BE5;
            IP &#x5730;&#x5740;&#x6216;&#x7B2C;&#x4E09;&#x65B9;&#x670D;&#x52A1;&#x5668;&#x53EF;&#x4EE5;&#x4E0B;&#x8F7D;&#x6587;&#x4EF6;&#x3002;</li>
        </ul>
        <p>&#x6CE8;&#xFF1A;</p>
        <ul>
          <li><code>allowedip</code> &#x53EA;&#x80FD;&#x586B;&#x5199;&#x4E00;&#x4E2A;
            IP &#x5730;&#x5740;&#x3002;</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

### 响应参数

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>&#x540D;&#x79F0;</b>
      </th>
      <th style="text-align:left"><b>&#x7C7B;&#x578B;</b>
      </th>
      <th style="text-align:left"><b>&#x63CF;&#x8FF0;</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>extid</code>
      </td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">&#x54EA;&#x4E2A;&#x5206;&#x673A;&#x7684;&#x8BED;&#x97F3;&#x7559;&#x8A00;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>voicemailfile</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x8BED;&#x97F3;&#x7559;&#x8A00;&#x6587;&#x4EF6;&#x7684;&#x540D;&#x79F0;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>random</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x8BED;&#x97F3;&#x7559;&#x8A00;&#x6587;&#x4EF6;&#x7684;&#x968F;&#x673A;&#x4E32;&#x3002;</p>
        <p>&#x4F7F;&#x7528;&#x8FD9;&#x4E2A;&#x968F;&#x673A;&#x4E32;&#x7EC4;&#x5408;&#x6210;&#x4E0B;&#x8F7D;&#x64AD;&#x653E;&#x8BE5;&#x5F55;&#x97F3;&#x6587;&#x4EF6;&#x8BF7;&#x6C42;&#x3002;</p>
      </td>
    </tr>
  </tbody>
</table>

### 实际示例

**请求示例**

```text
POST /api/v1.1.0/voicemail/get_random?token=1e3b3ebb6a974cb42ed31de5413df52d HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 192.168.5.150
{
    "extid": "1004",
    "voicemailfile": "msg0000.wav",
}
```

**响应示例**

```text
HTTP/1.1 200 OK
Access-control-allow-origin: *
Access-control-allow-methods: GET, POST, OPTIONS, PUT, DELETE
{
    "status": "Success",
    "extid": "1004",
    "voicemailfile": "msg0000.wav",
    "random": "70f477822e6a379d7359b2d926ea95a5"
}
```

### 语音留言下载链接示例

使用 API 响应的 random 随机串组合成语音留言下载链接。

语音留言下载链接格式：

http://{pbx ip}:{https port}/api/v0.0.1/voicemail/download?extid=｛extid｝&voicemailstatus=｛voicemailstatus｝&token=｛token｝&voicemailfile={voicemailfile}&random=｛random｝

下面是语音留言下载链接示例：

[  
http://172.16.101.37:9011/api/v1.1.0/voicemail/download?extid=102&token=1733765a8f15fef25c90075c394e6b45&voicemailfile=msg0001.wav&random=385d9c3cdf0fd31b90887d1b5815151b](
http://172.16.101.37:9011/api/v1.1.0/voicemail/download?extid=102&token=1733765a8f15fef25c90075c394e6b45&voicemailfile=msg0001.wav&random=385d9c3cdf0fd31b90887d1b5815151b)

