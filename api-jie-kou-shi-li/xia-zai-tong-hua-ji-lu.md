---
description: 下载指定分机或所有分机的通话记录。
---

# 下载通话记录

**下载步骤**

1. 获取通话记录文件的随机串。
2. 使用随机串，组合成通话记录文件的下载链接。

注： 随机串的有效时长为30秒。

### Endpoint

```text
POST /api/v0.0.1/cdr/get_random?token={token}
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
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x8BBE;&#x7F6E;&#x5206;&#x673A;&#x3002;</p>
        <ul>
          <li>&#x6240;&#x6709;&#x5206;&#x673A;&#xFF1A;&#x8BBE;&#x7F6E; <code>extid</code> &#x4E3A; <code>all</code>&#xFF0C;&#x8868;&#x793A;&#x4E0B;&#x8F7D;&#x6240;&#x6709;&#x5206;&#x673A;&#x7684;&#x901A;&#x8BDD;&#x8BB0;&#x5F55;&#x3002;</li>
          <li>&#x5355;&#x4E2A;&#x5206;&#x673A;&#xFF1A;&#x8BBE;&#x7F6E; <code>extid</code> &#x4E3A;&#x5206;&#x673A;&#x53F7;&#x7801;&#x3002;</li>
          <li>&#x591A;&#x4E2A;&#x5206;&#x673A;&#xFF1A;&#x8BBE;&#x7F6E; <code>extid</code> &#x4E3A;&#x5206;&#x673A;&#x53F7;&#x7801;&#xFF0C;&#x591A;&#x4E2A;&#x5206;&#x673A;&#x53F7;&#x7801;&#x4E4B;&#x95F4;&#x7528; <code>,</code> &#x9694;&#x5F00;&#x3002;&#x4F8B;&#x5982;&#xFF1A;<code>&quot;extid&quot;: &quot;1000,1001,1002&quot;</code>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>starttime</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x67E5;&#x8BE2;&#x901A;&#x8BDD;&#x8BB0;&#x5F55;&#x7684;&#x8D77;&#x59CB;&#x65F6;&#x95F4;&#x3002;</p>
        <p>&#x65F6;&#x95F4;&#x683C;&#x5F0F;&#xFF1A;<code>yyyy-mm-dd hh:mm:ss</code>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>endtime</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x67E5;&#x8BE2;&#x901A;&#x8BDD;&#x8BB0;&#x5F55;&#x7684;&#x7ED3;&#x675F;&#x65F6;&#x95F4;&#x3002;</p>
        <p>&#x65F6;&#x95F4;&#x683C;&#x5F0F;&#xFF1A;<code>yyyy-mm-dd hh:mm:ss</code>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>allowedip</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x8BBE;&#x7F6E;&#x5141;&#x8BB8;&#x4E0B;&#x8F7D;&#x901A;&#x8BDD;&#x8BB0;&#x5F55;&#x7684;&#x8BBE;&#x5907;
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
| `extid` | String | 分机。 |
| `starttime` | String | 查询通话记录的起始时间。 |
| `endtime` | String | 查询通话记录的结束时间。 |
| `random` | String | 通话记录文件的随机串。使用这个随机串组合成该通话录音文件的下载链接。 |

### 实际示例

**请求示例**

获取所有分机的通话记录的随机码。

```text
POST /api/v0.0.1/cdr/get_random?token=813b621cfe8eecf445a2ce1f4a079ffe HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
    "extid": "all",
    "starttime": "2020-05-18 00:00:00",
    "endtime": "2020-05-20 23:59:59
}
```

**响应示例**

```text
HTTP/1.1 200 OK
Access-control-allow-origin: *
Access-control-allow-methods: GET, POST, OPTIONS, PUT, DELETE
{
    "status": "Success",
    "extid": "all",
    "starttime": "2020-05-01 00:00:00",
    "endtime": "2020-05-05 23:59:59",
    "random": "9ec0ef42229c68406363d21e8a82ca31"
}
```

### 通话记录下载链接

使用随机串（random）组合成通话记录的下载链接。

通话记录文件的格式为CSV。查看通话记录参数说明。

**通话记录下载链接格式**：

http://{pbx ip}:{https port}/api/v0.0.1/cdr/download?extid={extid}&starttime={starttime}&endtime={endtime}&token={token}&random={random}

**通话记录下载链接示例**：

http://172.16.101.37:9011/api/v0.0.1/cdr/download?extid=all&starttime=2020-05-01 00:00:00&endtime=2020-05-05 23:59:59&token=1733765a8f15fef25c90075c394e6b45&random=6bbae3a53045c07c53b3222132987156

