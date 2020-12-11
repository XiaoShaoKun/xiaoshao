---
description: 添加并设置分机。
---

# 添加分机

### 请求地址

```text
POST /api/v0.0.1/extension/add?token={token}&type={type}
```

### 

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
      <td style="text-align:left"><code>number</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">&#x5206;&#x673A;&#x53F7;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>username</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x7528;&#x6237;&#x540D;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>callerid</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x5206;&#x673A;&#x6765;&#x7535;&#x663E;&#x793A;&#x540D;&#x79F0;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>registerpassword</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x6CE8;&#x518C;&#x5BC6;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>maxregistrations</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">&#x540C;&#x65F6;&#x6CE8;&#x518C;&#x6570;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>loginpassword</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x7528;&#x6237;&#x5BC6;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>email</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x90AE;&#x4EF6;&#x5730;&#x5740;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>mobile</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x7535;&#x8BDD;&#x53F7;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>hasvoicemail</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x8BED;&#x97F3;&#x90AE;&#x7BB1;&#x529F;&#x80FD;&#x3002;</p>
        <ul>
          <li>on&#xFF1A;&#x5F00;&#x542F; &#x3002;</li>
          <li>off&#xFF1A;&#x5173;&#x95ED;&#x3002;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>vmsecret</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">&#x8BED;&#x97F3;&#x90AE;&#x7BB1;&#x5BC6;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>enablevmtoemail</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x662F;&#x5426;&#x53D1;&#x9001;&#x8BED;&#x97F3;&#x90AE;&#x4EF6;&#x5230;&#x90AE;&#x7BB1;&#x3002;</p>
        <ul>
          <li>on&#xFF1A;&#x5F00;&#x542F; &#x3002;</li>
          <li>off&#xFF1A;&#x5173;&#x95ED;&#x3002;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>noanswerforward</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x65E0;&#x5E94;&#x7B54;&#x8F6C;&#x79FB;&#x3002;</p>
        <ul>
          <li>on&#xFF1A;&#x5F00;&#x542F;&#x3002;</li>
          <li>off&#xFF1A;&#x5173;&#x95ED;&#x3002;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ntransferto</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x65E0;&#x5E94;&#x7B54;&#x8F6C;&#x79FB;&#x76EE;&#x7684;&#x5730;&#x3002;</p>
        <ul>
          <li>Voicemail&#xFF1A;&#x8BED;&#x97F3;&#x4FE1;&#x7BB1;&#x3002;</li>
          <li>Extension&#xFF1A;&#x5206;&#x673A;&#x3002;</li>
          <li>Mobile Number&#xFF1A;&#x7528;&#x6237;&#x624B;&#x673A;&#x3002;</li>
          <li>Custom Number&#xFF1A;&#x81EA;&#x5B9A;&#x4E49;&#x53F7;&#x7801;&#x3002;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ntransferext</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x76EE;&#x7684;&#x5730;&#x4E3A;&#x5206;&#x673A;&#x65F6;&#x7684;&#x5206;&#x673A;&#x53F7;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ntransferprefix</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x76EE;&#x7684;&#x5730;&#x4E3A;&#x81EA;&#x5B9A;&#x4E49;&#x53F7;&#x7801;&#x6216;&#x7528;&#x6237;&#x624B;&#x673A;&#x65F6;&#x7684;&#x547C;&#x51FA;&#x524D;&#x7F00;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ntransfernum</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x76EE;&#x7684;&#x5730;&#x4E3A;&#x81EA;&#x5B9A;&#x4E49;&#x53F7;&#x7801;&#x6216;&#x7528;&#x6237;&#x624B;&#x673A;&#x65F6;&#x7684;&#x53F7;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>busyforward</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x5FD9;&#x65F6;&#x8F6C;&#x79FB;&#x3002;</p>
        <ul>
          <li>on&#xFF1A;&#x5F00;&#x542F;&#x3002;</li>
          <li>off&#xFF1A;&#x5173;&#x95ED;&#x3002;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>btransferto</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x5FD9;&#x65F6;&#x8F6C;&#x79FB;&#x76EE;&#x7684;&#x5730;&#x3002;</p>
        <ul>
          <li>Voicemail&#xFF1A;&#x8BED;&#x97F3;&#x4FE1;&#x7BB1;&#x3002;</li>
          <li>Extension&#xFF1A;&#x5206;&#x673A;&#x3002;</li>
          <li>Mobile Number&#xFF1A;&#x7528;&#x6237;&#x624B;&#x673A;&#x3002;</li>
          <li>Custom Number&#xFF1A;&#x81EA;&#x5B9A;&#x4E49;&#x53F7;&#x7801;&#x3002;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>btransferext</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x76EE;&#x7684;&#x5730;&#x4E3A;&#x5206;&#x673A;&#x65F6;&#x7684;&#x5206;&#x673A;&#x53F7;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>btransferprefix</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x76EE;&#x7684;&#x5730;&#x4E3A;&#x81EA;&#x5B9A;&#x4E49;&#x53F7;&#x7801;&#x6216;&#x7528;&#x6237;&#x624B;&#x673A;&#x65F6;&#x7684;&#x547C;&#x51FA;&#x524D;&#x7F00;&#x3002;&#x9650;&#x5236;&#xFF1A;
        &#x6570;&#x5B57;&#xFF0C;&#x6700;&#x5927;7&#x4F4D;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>btransfernum</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x76EE;&#x7684;&#x5730;&#x4E3A;&#x81EA;&#x5B9A;&#x4E49;&#x53F7;&#x7801;&#x6216;&#x7528;&#x6237;&#x624B;&#x673A;&#x65F6;&#x7684;&#x547C;&#x51FA;&#x53F7;&#x7801;&#x3002;&#x9650;&#x5236;&#xFF1A;
        &#x6570;&#x5B57;&#xFF0C;&#x6700;&#x5927;15&#x4F4D;&#xFF0C;&#x8F6C;&#x79FB;&#x76EE;&#x7684;&#x5730;Custom
        Number&#x4E0D;&#x4E3A;&#x7A7A;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>enablemobile</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x79FB;&#x52A8;&#x5206;&#x673A;&#x529F;&#x80FD;&#x3002;</p>
        <ul>
          <li>on&#xFF1A;&#x5F00;&#x542F; &#x3002;</li>
          <li>off&#xFF1A;&#x5173;&#x95ED;&#x3002;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ringsimultaneous</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x79FB;&#x52A8;&#x5206;&#x673A;&#x548C;&#x5206;&#x673A;&#x540C;&#x65F6;&#x54CD;&#x94C3;&#x3002;</p>
        <ul>
          <li>on&#xFF1A;&#x5F00;&#x542F; &#x3002;</li>
          <li>off&#xFF1A;&#x5173;&#x95ED;&#x3002;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>mobileprefix</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x79FB;&#x52A8;&#x5206;&#x673A;&#x547C;&#x51FA;&#x524D;&#x7F00;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>allowbeingmonitored</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
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
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x76D1;&#x542C;&#x6A21;&#x5F0F;&#x3002;</p>
        <ul>
          <li>Disabled&#xFF1A;&#x7981;&#x7528;&#x3002;</li>
          <li>Extensive&#xFF1A;&#x901A;&#x7528;&#x6A21;&#x5F0F;&#x3002;</li>
          <li>Listen&#xFF1A;&#x666E;&#x901A;&#x76D1;&#x542C;&#x3002;</li>
          <li>Whisper&#xFF1A;&#x5BC6;&#x8BED;&#x76D1;&#x542C;&#x3002;</li>
          <li>Barge-in&#xFF1A;&#x5F3A;&#x63D2;&#x76D1;&#x542C;&#x3002;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ringtimeout</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x54CD;&#x94C3;&#x8D85;&#x65F6;&#x3002;</p>
        <ul>
          <li>15</li>
          <li>30</li>
          <li>60</li>
          <li>120</li>
          <li>300</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>maxduration</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x6700;&#x5927;&#x901A;&#x8BDD;&#x65F6;&#x957F;&#x3002;</p>
        <ul>
          <li>Follow System&#xFF1A;&#x7CFB;&#x7EDF;&#x9ED8;&#x8BA4;&#x503C;&#x3002;</li>
          <li>Unlimited&#xFF1A;&#x65E0;&#x9650;&#x5236;&#x3002;</li>
          <li>60</li>
          <li>300</li>
          <li>600</li>
          <li>900</li>
          <li>1800</li>
          <li>3600</li>
          <li>6000</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>dnd</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x514D;&#x6253;&#x6270;&#x529F;&#x80FD;&#x3002;</p>
        <ul>
          <li>on&#xFF1A;&#x5F00;&#x542F;&#x3002;</li>
          <li>off&#xFF1A;&#x5173;&#x95ED;&#x3002;</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

### 响应参数

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
  </tbody>
</table>

### 示例

**请求示例**

添加分机2002。

```text
POST /api/v0.0.1/extension/add?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150

{
	"number":"2002",
	"username":"xiaoshao_api2",
	"callerid":"",
	"registerpassword":"12345133333323123qW@",
	"maxregistrations":"3",
	"loginpassword":"12345678qW@",
	"email":"897257036@qq.com",
	"mobile":"18088861612",
	"hasvoicemail":"on",
	"vmsecret":"888888",
	"enablevmtoemail":"on",
	"noanswerforward":"off",
	"ntransferto":"Extension",
	"ntransferext":"6000",
	"ntransferprefix":"",
	"busyforward":"off",
	"btransferto":"Extension",
	"btransferext":"110",
	"btransferprefix":"",
	"btransfernum":"",
	"enablemobile":"off",
	"ringsimultaneous":"off",
	"mobileprefix":"",
	"allowbeingmonitored":"off",
	"monitormode":"Disable",
	"ringtimeout":"15",
	"maxduration":"Follow System",
	"dnd":"off"
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
    "status": "Success"
}
```

```text
HTTP/1.1 200 OK
Access-control-allow-origin: *
Access-control-allow-methods: GET, POST, OPTIONS, PUT, DELETE
<?xml version="1.0" encoding="utf-8"?>
<xml>
	<status>Success</status>
</xml>
```

