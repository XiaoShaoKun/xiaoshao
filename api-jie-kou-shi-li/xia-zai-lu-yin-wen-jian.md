---
description: 通过本接口可获取 PBX 中的全局录音文件。
---

# 下载录音文件

**下载步骤**

1. 通过‘通话记录’报告中的`recording` 参数获取到全局录音文件的名称。
2. 通过获取到的名称从 PBX 获取有关该文件的一个随机串。
3. 通过该随机串组合成录音文件的下载链接。

注： 随机串的有效时长为30秒，并且每个随机串使用过一次则失效。

### Endpoint

```text
POST /api/v0.0.1/recording/get_random?token={token}
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
      <td style="text-align:left"><code>recording</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x5168;&#x5C40;&#x5F55;&#x97F3;&#x6587;&#x4EF6;&#x540D;&#x79F0;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>allowedip</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x8BBE;&#x7F6E;&#x5141;&#x8BB8;&#x4E0B;&#x8F7D;&#x5F55;&#x97F3;&#x6587;&#x4EF6;&#x7684;&#x8BBE;&#x5907;
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

| 名称 | 类型 | 描述 |
| :--- | :--- | :--- |
| `recording` | String | 全局录音文件名称。 |
| `random` | String | 有关全局录音文件的一个随机串。使用这个随机串组合成下载播放该录音文件请求。 |

### 实际示例

**请求示例**

请求录音文件的随机串。

```text
POST /api/v0.0.1/recording/get_random?token=813b621cfe8eecf445a2ce1f4a079ffe HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
	"recording":"exten-101-106-20200505-042135-1588641695.1772.wav",
	"allowedip":"172.16.6.150"
}
```

**响应示例**

```text
HTTP/1.1 200 OK
Access-control-allow-origin: *
Access-control-allow-methods: GET, POST, OPTIONS, PUT, DELETE
{
    "status": "Success",
    "recording": "exten-101-106-20200505-042135-1588641695.1772.wav",
    "random": "fc19203cddc1d7846c2236f9eafe826b"
}
```

### 全局录音下载链接

使用随机串（random）组合成录音文件的下载链接。

**录音下载链接格式**：

http://{pbx ip}:{https port}/api/v1.1.0/recording/download?recording={recording}&random={random}&token={token}

**录音下载链接示例**：

[http://172.16.101.37:9011/api/v1.1.0/recording/download?recording=exten-101-106-20200505-042135-1588641695.1772.wav&random=1c574a38b96a0a94fe631208ce30ae53&token=1733765a8f15fef25c90075c394e6b45](http://172.16.101.37:9011/api/v1.1.0/recording/download?recording=exten-101-106-20200505-042135-1588641695.1772.wav&random=1c574a38b96a0a94fe631208ce30ae53&token=1733765a8f15fef25c90075c394e6b45)

