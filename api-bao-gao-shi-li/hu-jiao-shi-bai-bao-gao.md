---
description: 当发起的呼叫失败时，PBX 会向应用服务器发送“呼叫失败”报告。
---

# ‘呼叫失败’报告

注： 只要是被叫方未接通的状况都定义为呼叫失败，转到语音留言算已接通。不管是 API 控制的呼叫还是手动拨号的呼叫，只要呼叫失败都会触发该事件。



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
      <td style="text-align:left">&#x547C;&#x53EB;&#x5931;&#x8D25;&#x4E8B;&#x4EF6;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>reason</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x547C;&#x53EB;&#x5931;&#x8D25;&#x539F;&#x56E0;&#xFF1A;</p>
        <ul>
          <li>480&#xFF1A;&#x88AB;&#x53EB;&#x6CA1;&#x6709;&#x63A5;&#x542C;&#x6765;&#x7535;&#x3002;</li>
        </ul>
      </td>
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
      <td style="text-align:left">Int</td>
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
      <td style="text-align:left">&#x539F;&#x59CB;&#x4E3B;&#x53EB;&#x53F7;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>to</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x539F;&#x59CB;&#x88AB;&#x53EB;&#x53F7;&#x7801;&#x3002;</td>
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

```text
POST  HTTP/1.1
Host:172.16.6.150
Content-Length:113
Accept: application/json
Content-Type:application/json
Connection:close

{
    "action":"CallFailed",
    "reason":480,
    "callid":"1589958470.2092",
    "ext":{
        "extid":[
            "102",
            "106"
        ]
    },
    "sn":"a09805021987"
}
```

