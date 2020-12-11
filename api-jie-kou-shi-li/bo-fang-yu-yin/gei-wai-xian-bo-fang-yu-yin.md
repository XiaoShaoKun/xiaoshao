---
description: 通过本接口可给外线号码播放语音，PBX 拨打外线，外线响铃接起后，听到提示音。
---

# 给外线播放语音



### Endpoint

```text
POST /api/v0.0.1/outbound/playprompt?token={token}
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
      <td style="text-align:left"><code>outto</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x5916;&#x7EBF;&#x53F7;&#x7801;&#x3002;</td>
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
        <p>&#x591A;&#x4E2A;&#x8BED;&#x97F3;&#x6587;&#x4EF6;&#x4E4B;&#x95F4;&#x7528;<code>+</code> &#x8FDE;&#x63A5;&#x3002;&#x4F8B;&#x5982;&#xFF1A;<code>&quot;prompt:music1+music2&quot;</code>
        </p>
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
POST /api/v0.0.1/outbound/playprompt?token=813b621cfe8eecf445a2ce1f4a079ffe HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
    "outto": "16103",
    "prompt": "haruhi3+xiaoshao5"
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

