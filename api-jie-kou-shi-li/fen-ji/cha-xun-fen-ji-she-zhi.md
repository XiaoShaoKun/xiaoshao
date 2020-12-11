---
description: 查询单个或者多个分机的详细信息，如：高级配置信息等。当发送查询多个分机请求的时候，请求参数需用逗号隔开。
---

# 查询分机设置



### Endpoint

```text
POST /api/v0.0.1/extension/query?token={token}&type={type}
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
        <p>&#x5206;&#x673A;&#x53F7;&#x7801;&#x3002;</p>
        <ul>
          <li>
            <p><b>&#x67E5;&#x8BE2;&#x5355;&#x4E2A;&#x5206;&#x673A;</b>&#xFF1A;&#x8BBE;&#x7F6E; <code>extid</code> &#x4E3A;&#x5206;&#x673A;&#x53F7;&#x7801;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;extid&quot;:&quot;1000&quot;</code>
            </p>
          </li>
          <li>
            <p><b>&#x67E5;&#x8BE2;&#x591A;&#x4E2A;&#x5206;&#x673A;</b>&#xFF1A;&#x8BBE;&#x7F6E; <code>extid</code> &#x4E3A;
              &#x5206;&#x673A;&#x53F7;&#x7801;&#xFF0C;&#x591A;&#x4E2A;&#x5206;&#x673A;&#x4E4B;&#x95F4;&#x7528; <code>,</code> &#x9694;&#x5F00;&#x3002;</p>
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
      <td style="text-align:left"><code>extinfos</code>
      </td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left">&#x5BF9;&#x8C61;&#x53C2;&#x6570;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>extnumber</code>
      </td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">&#x5206;&#x673A;&#x53F7;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>username</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x7528;&#x6237;&#x540D;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>status</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x5206;&#x673A;&#x5F53;&#x524D;&#x72B6;&#x6001;&#xFF1A;</p>
        <ul>
          <li>Unavailable&#xFF1A;&#x4E0D;&#x53EF;&#x4F7F;&#x7528;&#x3002;</li>
          <li>Registered&#xFF1A;&#x5DF2;&#x6CE8;&#x518C;&#x3002;</li>
          <li>Ringing&#xFF1A;&#x54CD;&#x94C3;&#x3002;</li>
          <li>Busy&#xFF1A;&#x5FD9;&#x7EBF;&#x3002;</li>
          <li>Hold&#xFF1A;&#x901A;&#x8BDD;&#x4FDD;&#x6301;&#x3002;</li>
          <li>Malfunction&#xFF1A;&#x6545;&#x969C;&#x3002;</li>
          <li>Idle&#xFF1A;&#x7A7A;&#x95F2;&#x3002;</li>
          <li>Fxsnoport</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>type</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x5206;&#x673A;&#x7C7B;&#x578B;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>port</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">FXS &#x5206;&#x673A;&#x7AEF;&#x53E3;&#x53F7;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>callerid</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x6765;&#x7535;&#x663E;&#x793A;&#x53F7;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>registerpassword</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x6CE8;&#x518C;&#x5BC6;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>maxregistrations</code>
      </td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">&#x540C;&#x65F6;&#x6CE8;&#x518C;&#x6570;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>loginpassword</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x7528;&#x6237;&#x5BC6;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>email</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x90AE;&#x4EF6;&#x5730;&#x5740;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>moblie</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x7535;&#x8BDD;&#x53F7;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>language</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x63D0;&#x793A;&#x97F3;&#x8BED;&#x8A00;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>hasvoicemail</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x542F;&#x7528;&#x8BED;&#x97F3;&#x90AE;&#x7BB1;&#x3002;</p>
        <ul>
          <li>on&#xFF1A;&#x5F00;&#x542F;&#x3002;</li>
          <li>off&#xFF1A;&#x5173;&#x95ED;&#x3002;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>vmsecret</code>
      </td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">&#x8BED;&#x97F3;&#x90AE;&#x7BB1;&#x5BC6;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>enablevmtoemail</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x53D1;&#x9001;&#x8BED;&#x97F3;&#x90AE;&#x4EF6;&#x5230;&#x90AE;&#x7BB1;&#x3002;</p>
        <ul>
          <li>on&#xFF1A;&#x5F00;&#x542F;&#x3002;</li>
          <li>off&#xFF1A;&#x5173;&#x95ED;&#x3002;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>noanswerforward</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x65E0;&#x5E94;&#x7B54;&#x8F6C;&#x79FB;&#x529F;&#x80FD;&#x3002;</p>
        <ul>
          <li>on&#xFF1A;&#x5F00;&#x542F;&#x3002;</li>
          <li>off&#xFF1A;&#x5173;&#x95ED;&#x3002;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><code>ntransferto</code>
        </p>
        <p><code>ntransferext</code>
        </p>
        <p><code>ntransferprefix</code>
        </p>
        <p><code>ntransfernum</code>
        </p>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x65E0;&#x5E94;&#x7B54;&#x8F6C;&#x79FB;&#x76EE;&#x7684;&#x5730;&#xFF0C;&#x5982;&#x679C;&#x9009;&#x62E9;&#x603B;&#x662F;&#x8F6C;&#x79FB;&#x5230;&#x5206;&#x673A;&#xFF0C;&#x5219;&#x9700;&#x8BBE;&#x7F6E;&#x8981;&#x8F6C;&#x79FB;&#x5230;&#x7684;&#x5206;&#x673A;&#x53F7;&#xFF1B;&#x5982;&#x679C;&#x603B;&#x662F;&#x8F6C;&#x79FB;&#x5230;&#x5916;&#x7EBF;&#x53F7;&#x7801;&#xFF0C;&#x5219;&#x9700;&#x8BBE;&#x7F6E;&#x8981;&#x8F6C;&#x79FB;&#x5230;&#x7684;&#x5916;&#x7EBF;&#x53F7;&#x7801;&#x4EE5;&#x53CA;&#x547C;&#x53EB;&#x89C4;&#x5219;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>busyforward</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x5FD9;&#x65F6;&#x8F6C;&#x79FB;&#x529F;&#x80FD;&#x3002;</p>
        <ul>
          <li>on&#xFF1A;&#x5F00;&#x542F;&#x3002;</li>
          <li>off&#xFF1A;&#x5173;&#x95ED;&#x3002;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">
        <p><code>btransferto</code>
        </p>
        <p><code>btransferext</code>
        </p>
        <p><code>btransferprefix</code>
        </p>
        <p><code>btransfernum</code>
        </p>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x5FD9;&#x65F6;&#x8F6C;&#x79FB;&#x76EE;&#x7684;&#x5730;&#xFF0C;&#x5982;&#x679C;&#x9009;&#x62E9;&#x603B;&#x662F;&#x8F6C;&#x79FB;&#x5230;&#x5206;&#x673A;&#xFF0C;&#x5219;&#x9700;&#x8BBE;&#x7F6E;&#x8981;&#x8F6C;&#x79FB;&#x5230;&#x7684;&#x5206;&#x673A;&#x53F7;&#xFF1B;&#x5982;&#x679C;&#x603B;&#x662F;&#x8F6C;&#x79FB;&#x5230;&#x5916;&#x7EBF;&#x53F7;&#x7801;&#xFF0C;&#x5219;&#x9700;&#x8BBE;&#x7F6E;&#x8981;&#x8F6C;&#x79FB;&#x5230;&#x7684;&#x5916;&#x7EBF;&#x53F7;&#x7801;&#x4EE5;&#x53CA;&#x547C;&#x53EB;&#x89C4;&#x5219;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>enablemobile</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x79FB;&#x52A8;&#x5206;&#x673A;&#x529F;&#x80FD;&#x3002;</p>
        <ul>
          <li>on&#xFF1A;&#x5F00;&#x542F;&#x3002;</li>
          <li>off&#xFF1A;&#x5173;&#x95ED;&#x3002;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ringsimultaneous</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x79FB;&#x52A8;&#x5206;&#x673A;&#x4E0E;&#x5206;&#x673A;&#x540C;&#x65F6;&#x54CD;&#x94C3;&#x3002;</p>
        <ul>
          <li>on&#xFF1A;&#x5F00;&#x542F;&#x3002;</li>
          <li>off&#xFF1A;&#x5173;&#x95ED;&#x3002;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>mobileprefix</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x79FB;&#x52A8;&#x5206;&#x673A;&#x547C;&#x51FA;&#x524D;&#x7F00;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>allowbeingmonitored</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x5141;&#x8BB8;&#x88AB;&#x76D1;&#x542C;&#x3002;</p>
        <ul>
          <li>on&#xFF1A;&#x5F00;&#x542F;&#x3002;</li>
          <li>off&#xFF1A;&#x5173;&#x95ED;&#x3002;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>monitormode</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x76D1;&#x542C;&#x6A21;&#x5F0F;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ringtimeout</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x54CD;&#x94C3;&#x8D85;&#x65F6;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>maxduration</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x6700;&#x5927;&#x901A;&#x8BDD;&#x65F6;&#x957F;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>dnd</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x514D;&#x6253;&#x6270;&#x529F;&#x80FD;&#x3002;</p>
        <ul>
          <li>on&#xFF1A;&#x5F00;&#x542F;&#x3002;</li>
          <li>off&#xFF1A;&#x5173;&#x95ED;&#x3002;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>inbound</code>
      </td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left">&#x6765;&#x7535;&#xFF0C;&#x547C;&#x5165;&#x7684;&#x5916;&#x7EBF;&#x901A;&#x8BDD;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>inboundid</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x6765;&#x7535;&#x7684;&#x7F16;&#x53F7;&#xFF0C;&#x4F9D;&#x636E;&#x8BE5;&#x53C2;&#x6570;&#x5BF9;&#x6765;&#x7535;&#x8FDB;&#x884C;&#x8F6C;&#x63A5;&#x3001;&#x67E5;&#x8BE2;&#x3001;&#x6302;&#x65AD;&#x7B49;&#x64CD;&#x4F5C;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>from</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x4E3B;&#x53EB;&#x53F7;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>to</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x88AB;&#x53EB;&#x53F7;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>trunk</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x547C;&#x5165;&#x65F6;&#x901A;&#x8FC7;&#x7684;&#x4E2D;&#x7EE7;&#x540D;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>outbound</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x53BB;&#x7535;&#xFF0C;&#x547C;&#x51FA;&#x5230;&#x5916;&#x7EBF;&#x7684;&#x901A;&#x8BDD;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>outboundid</code>
      </td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left">&#x53BB;&#x7535;&#x7684;&#x7F16;&#x53F7;&#xFF0C;&#x4F9D;&#x636E;&#x8BE5;&#x53C2;&#x6570;&#x5BF9;&#x6765;&#x7535;&#x8FDB;&#x884C;&#x8F6C;&#x63A5;&#x3001;&#x67E5;&#x8BE2;&#x3001;&#x6302;&#x65AD;&#x7B49;&#x64CD;&#x4F5C;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>from</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x4E3B;&#x53EB;&#x53F7;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>to</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x88AB;&#x53EB;&#x53F7;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>trunk</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x547C;&#x51FA;&#x65F6;&#x901A;&#x8FC7;&#x7684;&#x4E2D;&#x7EE7;&#x540D;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ext</code>
      </td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left">&#x5185;&#x90E8;&#x5206;&#x673A;&#x4E92;&#x62E8;&#x7684;&#x901A;&#x8BDD;&#x65B9;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>extid</code>
      </td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">&#x548C;&#x67E5;&#x8BE2;&#x5206;&#x673A;&#x6B63;&#x5728;&#x901A;&#x8BDD;&#x7684;&#x5206;&#x673A;&#x53F7;&#x3002;</td>
    </tr>
  </tbody>
</table>

### 实际示例

**请求示例**

查询分机101。

```text
POST /api/v1.1.0/extension/query?token=277ac400357b509b4a587ff2157f7ad5&type=json HTTP/1.1 HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
    "extid": "101"
}
```



```text
POST /api/v1.1.0/extension/query?token=277ac400357b509b4a587ff2157f7ad5&type=xml HTTP/1.1 HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
<?xml version="1.0" encoding="utf-8"?>
<xml>
	<extid>101</extid>
</xml>
```

查询所有分机。

```text
POST /api/v0.0.1/extension/query?token=277ac400357b509b4a587ff2157f7ad5 HTTP/1.1 HTTP/1.1
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
    "extinfos": [
        {
            "extnumber": "101",
            "username": "xiaoshaokun",
            "type": "pjsip",
            "noanswerforward": "off",
            "busyforward": "off",
            "status": "Unavailable",
            "callerid": "858585",
            "userpassword": "12345678qW@",
            "registerpassword": "12345133333323123qW@",
            "email": "897257036@qq.com",
            "moblie": "18088861612",
            "maxregistrations": "3",
            "hasvoicemail": "on",
            "vmsecret": "666666",
            "enablevmtoemail": "on",
            "language": "cn",
            "allowbeingmonitored": "off",
            "monitormode": "disable",
            "maxduration": "10800",
            "dnd": "off"
        }
    ]
}
```

```text
HTTP/1.1 200 OK
Access-control-allow-origin: *
Access-control-allow-methods: GET, POST, OPTIONS, PUT, DELETE
<?xml version="1.0" encoding="utf-8"?>
<xml>
	<status>Success</status>
	<extinfos>
		<item id="0">
			<extnumber>101</extnumber>
			<username>xiaoshaokun</username>
			<type>pjsip</type>
			<noanswerforward>off</noanswerforward>
			<busyforward>off</busyforward>
			<status>Unavailable</status>
			<callerid>888888</callerid>
			<registerpassword>12345133333323123qW@</registerpassword>
			<email>897257036@qq.com</email>
			<moblie>18088861612</moblie>
			<maxregistrations>3</maxregistrations>
			<hasvoicemail>on</hasvoicemail>
			<vmsecret>666666</vmsecret>
			<userpassword>12345678qW@</userpassword>
			<enablevmtoemail>on</enablevmtoemail>
			<language>cn</language>
			<allowbeingmonitored>off</allowbeingmonitored>
			<monitormode>disable</monitormode>
			<maxduration>10800</maxduration>
			<dnd>off</dnd>
		</item>
	</extinfos>
</xml>
```

