---
description: 修改队列的配置，如：修改队列号码、名称等。
---

# 编辑队列设置



### Endpoint

```text
POST /api/v0.0.1/queue/update?token={token}&type={type}
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
      <td style="text-align:left"><code>queueid</code>
      </td>
      <td style="text-align:left">&#x662F;</td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">&#x8981;&#x4FEE;&#x6539;&#x7684;&#x961F;&#x5217;&#x53F7;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>queuename</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x961F;&#x5217;&#x540D;&#x79F0;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>password</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x52A0;&#x5165;&#x52A8;&#x6001;&#x5750;&#x5E2D;&#x7684;&#x5BC6;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ringstrategy</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x54CD;&#x94C3;&#x7B56;&#x7565;&#x3002;</p>
        <ul>
          <li>Ring All&#xFF1A;&#x5168;&#x90E8;&#x54CD;&#x94C3;</li>
          <li>Least Recent&#xFF1A;&#x6700;&#x8FD1;&#x6700;&#x5C11;&#x88AB;&#x53EB;&#x54CD;&#x94C3;</li>
          <li>Fewest Calls&#xFF1A;&#x6700;&#x5C11;&#x63A5;&#x901A;&#x54CD;&#x94C3;</li>
          <li>Random&#xFF1A;&#x968F;&#x673A;&#x54CD;&#x94C3;</li>
          <li>Rrmemory&#xFF1A;&#x987A;&#x5E8F;&#x54CD;&#x94C3;</li>
          <li>Linear&#xFF1A;&#x7EBF;&#x6027;&#x54CD;&#x94C3;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>agents</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x56FA;&#x5B9A;&#x5EA7;&#x5E2D;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>dynamicagents</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x52A8;&#x6001;&#x5750;&#x5E2D;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>agenttimeout</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x5750;&#x5E2D;&#x54CD;&#x94C3;&#x65F6;&#x95F4;</p>
        <p>&#x53EF;&#x9009;&#x503C;&#xFF1A; 10&#x3001;20&#x3001;30&#x3001;40&#x3001;50</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>wrapuptime</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">
        <p>&#x4F11;&#x606F;&#x65F6;&#x95F4;</p>
        <p>&#x53EF;&#x9009;&#x503C;&#xFF1A;10&#x3001;20&#x3001;30&#x3001;40&#x3001;50</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>retry</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">
        <p>&#x91CD;&#x8BD5;&#x95F4;&#x9694;&#x65F6;&#x95F4;</p>
        <p>&#x53EF;&#x9009;&#x503C;&#xFF1A;10&#x3001;20&#x3001;30&#x3001;40&#x3001;50</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>maxwaittime</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">
        <p>&#x6700;&#x5927;&#x7B49;&#x5F85;&#x65F6;&#x95F4;</p>
        <p>&#x53EF;&#x9009;&#x503C;&#xFF1A;300&#x3001;600&#x3001;900&#x3001;1200&#x3001;1800</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>joinempty</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x65E0;&#x5EA7;&#x5E2D;&#x65F6;&#x5141;&#x8BB8;&#x547C;&#x5165;</p>
        <ul>
          <li>on&#xFF1A;&#x5F00;&#x542F;&#x3002;</li>
          <li>off&#xFF1A;&#x5173;&#x95ED;&#x3002;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>leavewhenempty</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x65E0;&#x5EA7;&#x5E2D;&#x65F6;&#x7ED3;&#x675F;&#x7B49;&#x5F85;</p>
        <ul>
          <li>on&#xFF1A;&#x5F00;&#x542F;&#x3002;</li>
          <li>off&#xFF1A;&#x5173;&#x95ED;&#x3002;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>announcepos</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x516C;&#x544A;&#x5F53;&#x524D;&#x4F4D;&#x7F6E;</p>
        <ul>
          <li>on&#xFF1A;&#x5F00;&#x542F;&#x3002;</li>
          <li>off&#xFF1A;&#x5173;&#x95ED;&#x3002;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>announcefreq</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x7528;&#x6237;&#x516C;&#x544A;&#x9891;&#x7387;</p>
        <p>&#x53EF;&#x9009;&#x503C;&#xFF1A;0&#x3001;15&#x3001;30&#x3001;45&#x3001;60&#x3001;120&#x3001;180&#x3001;240&#x3001;300&#x3001;600&#x3001;1200</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>announceholdtime</code>
      </td>
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">
        <p>&#x516C;&#x544A;&#x7B49;&#x5F85;&#x65F6;&#x95F4;</p>
        <ul>
          <li>on&#xFF1A;&#x5F00;&#x542F;&#x3002;</li>
          <li>off&#xFF1A;&#x5173;&#x95ED;&#x3002;</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>



### 实际示例

**请求示例**

```text
POST /api/v0.0.1/queue/update?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
	"queueid":"9998",
	"queuename":"queue_xiaoshao",
	"password":"666666",
	"ringstrategy":"Ring All",
	"agents":"101",
	"dynamicagents":"6000",
	"agenttimeout":"20",
	"wrapuptime":"10",
	"retry":"10",
	"maxwaittime":"600",
	"joinempty":"on",
	"leavewhenempty":"off",
	"announcepos":"off",
	"announcefreq":"300",
	"announceholdtime":"off"
}
```

```text
POST /api/v0.0.1/queue/update?token=813b621cfe8eecf445a2ce1f4a079ffe&type=xml HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
	<queueid>9998</queueid>
	<queuename>queue_xiaoshao</queuename>
	<password>666666</password>
	<ringstrategy>Ring All</ringstrategy>
	<agents>101</agents>
	<dynamicagents>6000</dynamicagents>
	<agenttimeout>20</agenttimeout>
	<wrapuptime>10</wrapuptime>
	<retry>10</retry>
	<maxwaittime>600</maxwaittime>
	<joinempty>on</joinempty>
	<leavewhenempty>off</leavewhenempty>
	<announcepos>off</announcepos>
	<announcefreq>300</announcefreq>
	<announceholdtime>off</announceholdtime>
</xml>

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

```text
HTTP/1.1 200 OK
Access-control-allow-origin: *
Access-control-allow-methods: GET, POST, OPTIONS, PUT, DELETE
<?xml version="1.0" encoding="utf-8"?>
<xml>
	<status>Success</status>
</xml>
```

