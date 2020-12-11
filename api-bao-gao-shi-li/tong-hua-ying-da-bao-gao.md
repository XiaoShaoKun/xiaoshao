---
description: 当分机接听内部来电或外部来电时，PBX 会向应用服务器发送“通话应答”报告。
---

# ‘通话应答’报告

注： 应答和被应答事件同时一一对应，通话两方，主叫方为被应答，被叫方为应答，两个事件同时存在。报告时，被叫在主叫的前面。

### 报告参数

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x540D;&#x79F0;</th>
      <th style="text-align:left">&#x7C7B;&#x578B;</th>
      <th style="text-align:left">&#x63CF;&#x8FF0;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>action</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x901A;&#x8BDD;&#x5E94;&#x7B54;&#x4E8B;&#x4EF6;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>callid</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x8BE5;&#x901A;&#x901A;&#x8BDD;&#x7684; id&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ext</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x5206;&#x673A;&#x5BF9;&#x8C61;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>extid</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x5206;&#x673A;&#x53F7;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><code>inboundid</code>
        </p>
        <p><code>outboundid</code>
        </p>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x6765;&#x7535;&#x7F16;&#x7801;&#x6216;&#x53BB;&#x7535;&#x7F16;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><code>outbound</code>
        </p>
        <p><code>inbound</code>
        </p>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x5BF9;&#x8C61;&#x53C2;&#x6570;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>from</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x6765;&#x7535;&#x7684;&#x539F;&#x59CB;&#x4E3B;&#x53EB;&#x53F7;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>to</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x6765;&#x7535;&#x7684;&#x539F;&#x59CB;&#x88AB;&#x53EB;&#x53F7;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>trunk</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x901A;&#x8FC7;&#x54EA;&#x6761;&#x4E2D;&#x7EE7;&#x547C;&#x5165;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>sn</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">PBX &#x7684; SN &#x7801;&#x3002;</td>
    </tr>
  </tbody>
</table>



### 报告示例

分机101拨打分机106 106接听电话。

```text
POST  HTTP/1.1
Host:172.16.6.150
Content-Length:96
Accept: application/json
Content-Type:application/json
Connection:close

{
    "action":"ANSWER",
    "callid":"1589953310.1724",
    "ext":{
        "extid":[
            "106",
            "101"
        ]
    },
    "sn":"a09805021987"
}
```

外部用户 103呼叫分机 101，分机 101接听来电。

```text
POST  HTTP/1.1
Host:172.16.6.150
Content-Length:175
Accept: application/json
Content-Type:application/json
Connection:close

{
    "action":"ANSWER",
    "callid":"1589953417.1743",
    "ext":{
        "extid":"101"
    },
    "inbound":{
        "from":"103",
        "to":"101",
        "trunk":"to-18-16-2",
        "inboundid":"1589953417.1743"
    },
    "sn":"a09805021987"
}
```

