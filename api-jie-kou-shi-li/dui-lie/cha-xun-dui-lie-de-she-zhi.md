---
description: 查询单个或多个队列的详细信息，如：队列号码、队列名称、静态坐席、动态坐席等。
---

# 查询队列的设置



### Endpoint

```text
POST /api/v1.1.0/queue/query?token={token}&type={type}
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
      <td style="text-align:left">&#x5426;</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x961F;&#x5217;&#x53F7;&#x7801;&#x3002;</p>
        <ul>
          <li>
            <p><b>&#x67E5;&#x8BE2;&#x5355;&#x4E2A;&#x961F;&#x5217;</b>&#xFF1A;&#x8BBE;&#x7F6E; <code>queueid</code> &#x4E3A;
              IVR &#x53F7;&#x7801;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;queueid&quot;:&quot;6700&quot;</code>
            </p>
          </li>
          <li>
            <p><b>&#x67E5;&#x8BE2;&#x591A;&#x4E2A;&#x961F;&#x5217;</b>&#xFF1A;&#x8BBE;&#x7F6E; <code>queueid</code> &#x4E3A;
              IVR &#x53F7;&#x7801;&#xFF0C;&#x591A;&#x4E2A; IVR &#x4E4B;&#x95F4;&#x7528; <code>,</code> &#x9694;&#x5F00;&#x3002;</p>
            <p>&#x4F8B;&#x5982;&#xFF1A;<code>&quot;queueid&quot;: &quot;6700,6701,6702&quot;</code>
            </p>
          </li>
          <li><b>&#x67E5;&#x8BE2;&#x6240;&#x6709;&#x961F;&#x5217;</b>&#xFF1A;&#x4E0D;&#x5E26; <code>queueid</code> &#x8BF7;&#x6C42;&#x53C2;&#x6570;&#x3002;</li>
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
      <td style="text-align:left"><code>queues</code>
      </td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left">&#x5BF9;&#x8C61;&#x53C2;&#x6570;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>queuenumber</code>
      </td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">&#x961F;&#x5217;&#x53F7;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>queuename</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x961F;&#x5217;&#x53F7;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>password</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x52A0;&#x5165;&#x52A8;&#x6001;&#x5750;&#x5E2D;&#x7684;&#x5BC6;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>ringstrategy</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x54CD;&#x94C3;&#x7B56;&#x7565;&#x3002;</p>
        <ul>
          <li>Ring All</li>
          <li>Least Recent</li>
          <li>Fewest Calls</li>
          <li>Random</li>
          <li>Rrmemory</li>
          <li>Linear</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>agents</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x56FA;&#x5B9A;&#x5750;&#x5E2D;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>dynamicagents</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x52A8;&#x6001;&#x5750;&#x5E2D;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>agenttimeout</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x5750;&#x5E2D;&#x54CD;&#x94C3;&#x65F6;&#x95F4;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>agentannounce</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x5750;&#x5E2D;&#x5E94;&#x7B54;&#x63D0;&#x793A;&#x97F3;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>wrapuptime</code>
      </td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">&#x4F11;&#x606F;&#x65F6;&#x95F4;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>retry</code>
      </td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">&#x91CD;&#x8BD5;&#x95F4;&#x9694;&#x65F6;&#x95F4;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>musiconhold</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x7B49;&#x5F85;&#x97F3;&#x4E50;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>maxwaittime</code>
      </td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">&#x6700;&#x5927;&#x7B49;&#x5F85;&#x65F6;&#x95F4;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>joinempty</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x65E0;&#x5EA7;&#x5E2D;&#x65F6;&#x5141;&#x8BB8;&#x547C;&#x5165;&#x3002;</p>
        <ul>
          <li>on&#xFF1A;&#x542F;&#x7528;&#x3002;</li>
          <li>off&#xFF1A;&#x5173;&#x95ED;&#x3002;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>leavewhenempty</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x65E0;&#x5EA7;&#x5E2D;&#x65F6;&#x7ED3;&#x675F;&#x7B49;&#x5F85;&#x3002;</p>
        <ul>
          <li>on&#xFF1A;&#x542F;&#x7528;&#x3002;</li>
          <li>off&#xFF1A;&#x5173;&#x95ED;&#x3002;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>announcepos</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x516C;&#x544A;&#x5F53;&#x524D;&#x4F4D;&#x7F6E;&#x3002;</p>
        <ul>
          <li>on&#xFF1A;&#x542F;&#x7528;&#x3002;</li>
          <li>off&#xFF1A;&#x5173;&#x95ED;&#x3002;</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>announcefreq</code>
      </td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x7528;&#x6237;&#x516C;&#x544A;&#x9891;&#x7387;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>announceholdtime</code>
      </td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">&#x516C;&#x544A;&#x7B49;&#x5F85;&#x65F6;&#x95F4;&#x3002;</td>
    </tr>
  </tbody>
</table>

### 实际示例

**请求示例**

查询队列9999，9998。

```text
POST /api/v0.0.1/queue/query?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
    "queueid": "9999,9998"
}
```

```text
POST /api/v0.0.1/queue/query?token=813b621cfe8eecf445a2ce1f4a079ffe&type=xml HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
	<queueid>9999,9998</queueid>
</xml>
```

查询所有队列。

```text
POST /api/v0.0.1/queue/query?token=813b621cfe8eecf445a2ce1f4a079ffe HTTP/1.1
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
    "queues": [
        {
            "queuenumber": "9998",
            "queuename": "queue_xiaoshao",
            "password": "666666",
            "agents": "101",
            "announcefreq": "300",
            "announceholdtime": "off",
            "announcepos": "off",
            "joinempty": "on",
            "leavewhenempty": "off",
            "retry": "10",
            "ringstrategy": "Ring All",
            "agenttimeout": "20",
            "wrapuptime": "10",
            "dynamicagents": "6000",
            "agentannounce": "",
            "musiconhold": "Inherit",
            "maxwaittime": "600"
        },
        {
            "queuenumber": "9999",
            "queuename": "queue_test",
            "password": "123456",
            "agents": "101,103,104",
            "announcefreq": "0",
            "announceholdtime": "off",
            "announcepos": "off",
            "joinempty": "on",
            "leavewhenempty": "off",
            "retry": "5",
            "ringstrategy": "Ring All",
            "agenttimeout": "15",
            "wrapuptime": "60",
            "dynamicagents": "",
            "agentannounce": "",
            "musiconhold": "Inherit",
            "maxwaittime": "5"
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
	<queues>
		<item id="0">
			<queuenumber>9998</queuenumber>
			<queuename>queue_xiaoshao</queuename>
			<password>666666</password>
			<agents>101</agents>
			<announcefreq>300</announcefreq>
			<announceholdtime>off</announceholdtime>
			<announcepos>off</announcepos>
			<joinempty>on</joinempty>
			<leavewhenempty>off</leavewhenempty>
			<retry>10</retry>
			<ringstrategy>Ring All</ringstrategy>
			<agenttimeout>20</agenttimeout>
			<wrapuptime>10</wrapuptime>
			<dynamicagents>6000</dynamicagents>
			<agentannounce></agentannounce>
			<musiconhold>Inherit</musiconhold>
			<maxwaittime>600</maxwaittime>
		</item>
		<item id="1">
			<queuenumber>9999</queuenumber>
			<queuename>queue_test</queuename>
			<password>123456</password>
			<agents>101,103,104</agents>
			<announcefreq>0</announcefreq>
			<announceholdtime>off</announceholdtime>
			<announcepos>off</announcepos>
			<joinempty>on</joinempty>
			<leavewhenempty>off</leavewhenempty>
			<retry>5</retry>
			<ringstrategy>Ring All</ringstrategy>
			<agenttimeout>15</agenttimeout>
			<wrapuptime>60</wrapuptime>
			<dynamicagents></dynamicagents>
			<agentannounce></agentannounce>
			<musiconhold>Inherit</musiconhold>
			<maxwaittime>5</maxwaittime>
		</item>
	</queues>
</xml>
```

