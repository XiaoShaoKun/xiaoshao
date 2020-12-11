---
description: 查询单个分机、多个分机的闹铃信息。
---

# 查询闹铃

### 请求地址

```text
POST /api/v0.0.1/wakeupcall/query?token={token}&type={type}
```

### 请求参数

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x53C2;&#x6570;</th>
      <th style="text-align:left">&#x662F;&#x5426;&#x5FC5;&#x9009;</th>
      <th style="text-align:left">&#x7C7B;&#x578B;</th>
      <th style="text-align:left">&#x63CF;&#x8FF0;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">number</td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x5206;&#x673A;&#x53F7;&#x7801;&#x3002;</p>
        <p><b>&#x53D6;&#x503C;&#x8303;&#x56F4;</b>&#xFF1A;</p>
        <ul>
          <li>
            <p>&#x5355;&#x4E2A;&#x5206;&#x673A;&#x53F7;&#x7801;&#xFF1A;&#x67E5;&#x8BE2;&#x6307;&#x5B9A;&#x5206;&#x673A;&#x7684;&#x95F9;&#x94C3;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;number&quot;:&quot;114&quot;</code>
            </p>
          </li>
          <li>
            <p>&#x591A;&#x4E2A;&#x5206;&#x673A;&#x53F7;&#x7801;&#xFF1A;&#x67E5;&#x8BE2;&#x591A;&#x4E2A;&#x5206;&#x673A;&#x7684;&#x95F9;&#x94C3;&#x3002;&#x591A;&#x4E2A;&#x5206;&#x673A;&#x53F7;&#x7801;&#x7528;&#x534A;&#x89D2;&#x9017;&#x53F7;&#xFF08;,&#xFF09;&#x9694;&#x5F00;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;number&quot;:&quot;110,114&quot;</code>
            </p>
          </li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

### 响应参数

注： 如果查询的分机没有闹铃信息，PBX 只响应请求成功或请求失败的参数。

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x53C2;&#x6570;</th>
      <th style="text-align:left">&#x7C7B;&#x578B;</th>
      <th style="text-align:left">&#x63CF;&#x8FF0;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">status</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x8BF7;&#x6C42;&#x7ED3;&#x679C;&#x3002;</p>
        <ul>
          <li>Success&#xFF1A;&#x6210;&#x529F;&#x3002;</li>
          <li>Failed&#xFF1A;&#x5931;&#x8D25;&#x3002;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">wakeups</td>
      <td style="text-align:left">Array &lt;WakeupInfo&gt;</td>
      <td style="text-align:left">&#x95F9;&#x94C3;&#x5217;&#x8868;&#x3002;</td>
    </tr>
  </tbody>
</table>

WakeupInfo

| 参数 | 类型 | 描述 |
| :--- | :--- | :--- |
| number | String | 分机号码。 |
| wakeup | Array &lt;ExtensionWakeup&gt; | 分机闹铃信息列表。 |

ExtensionWakeup

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x53C2;&#x6570;</th>
      <th style="text-align:left">&#x7C7B;&#x578B;</th>
      <th style="text-align:left">&#x63CF;&#x8FF0;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">wakeupid</td>
      <td style="text-align:left">Integer</td>
      <td style="text-align:left">&#x95F9;&#x94C3;&#x7684;&#x552F;&#x4E00; ID&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">time</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x95F9;&#x94C3;&#x65F6;&#x95F4;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">type</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x95F9;&#x94C3;&#x7C7B;&#x578B;&#x3002;</p>
        <ul>
          <li>onetime&#xFF1A;&#x4E00;&#x6B21;&#x3002;</li>
          <li>custom&#xFF1A;&#x81EA;&#x5B9A;&#x4E49;&#x3002;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">weekdays</td>
      <td style="text-align:left">Integer</td>
      <td style="text-align:left">
        <p><code>type</code> &#x4E3A; <code>custom</code> &#x65F6;&#xFF0C;&#x95F9;&#x94C3;&#x9002;&#x7528;&#x7684;&#x661F;&#x671F;&#x3002;</p>
        <ul>
          <li>0</li>
          <li>1</li>
          <li>2</li>
          <li>3</li>
          <li>4</li>
          <li>5</li>
          <li>6</li>
        </ul>
        <p>&#x5176;&#x4E2D;&#xFF0C;0&#x8868;&#x793A;&#x5468;&#x65E5;&#xFF0C;1-6&#x8868;&#x793A;&#x5468;&#x4E00;&#x5230;&#x5468;&#x516D;&#x3002;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">prompt</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x95F9;&#x94C3;&#x63D0;&#x793A;&#x97F3;&#x3002;</td>
    </tr>
  </tbody>
</table>

### 示例

**请求示例**

查询分机114的闹铃信息。

```text
POST /api/v0.0.1/wakeupcall/query?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150

{
    "number":"114"
}
```

**响应示例**

```text
HTTP/1.1 200 OK
Accept-Ranges: bytes
Connection: close
Content-Type: application/json
Access-control-allow-origin: *
Access-control-allow-methods: GET, POST, OPTIONS, PUT, DELETE

{
    "status": "Success",
    "wakeups": [
        {
            "number": "114",
            "wakeup": [
                {
                    "wakeupid": "10",
                    "type": "custom",
                    "weekdays": "0,1,2,3,5",
                    "time": "15:55",
                    "prompt": "custom/test"
                }
            ]
        }
    ]
}
```

