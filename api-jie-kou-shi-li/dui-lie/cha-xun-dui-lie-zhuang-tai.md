---
description: 查询队列坐席的状态。
---

# 查询队列状态



### Endpoint

```text
POST /api/v0.0.1/queuestatus/query?token={token}&type={type}
```

### 请求参数

| **名称** | **是否必需** | **类型** | **描述** |
| :--- | :--- | :--- | :--- |
| queueid | 是 | Int | 队列号码。 |

### 响应参数

<table>
  <thead>
    <tr>
      <th style="text-align:left"><b>&#x540D;&#x79F0;</b>
      </th>
      <th style="text-align:left"><b>&#x7C7B;&#x578B;</b>
      </th>
      <th style="text-align:left"><b>&#x63CF;&#x8FF0;</b>
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">queues</td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left">&#x961F;&#x5217;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">queuenumber</td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">&#x961F;&#x5217;&#x53F7;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">queuestatus</td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left">&#x961F;&#x5217;&#x72B6;&#x6001;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">callercount</td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">&#x5F53;&#x524D;&#x961F;&#x5217;&#x7B49;&#x5019;&#x4EBA;&#x6570;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">members</td>
      <td style="text-align:left">Object</td>
      <td style="text-align:left">&#x961F;&#x5217;&#x6210;&#x5458;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">agent</td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">&#x5750;&#x5E2D;&#x53F7;&#x7801;&#x3002;</td>
    </tr>
    <tr>
      <td style="text-align:left">agentstatus</td>
      <td style="text-align:left">Int</td>
      <td style="text-align:left">
        <p>&#x5750;&#x5E2D;&#x72B6;&#x6001;&#x3002;</p>
        <ul>
          <li>0-Unknown&#xFF1A;&#x672A;&#x77E5;</li>
          <li>1-Not In Use&#xFF1A;&#x5750;&#x5E2D;&#x5904;&#x4E8E;&#x7A7A;&#x95F2;&#x72B6;&#x6001;</li>
          <li>2-In Use&#xFF1A;&#x5750;&#x5E2D;&#x5904;&#x4E8E;&#x901A;&#x8BDD;&#x4E2D;</li>
          <li>3-Busy&#xFF1A;&#x672A;&#x77E5;</li>
          <li>4-Invalid&#xFF1A;&#x672A;&#x77E5;</li>
          <li>5-Unavailable&#xFF1A;&#x5750;&#x5E2D;&#x5206;&#x673A;&#x672A;&#x6CE8;&#x518C;&#x4E0A;</li>
          <li>6-Ringing&#xFF1A;&#x5750;&#x5E2D;&#x5206;&#x673A;&#x6B63;&#x5728;&#x54CD;&#x94C3;</li>
          <li>7-In Use Ringing&#xFF1A;&#x5750;&#x5E2D;&#x901A;&#x8BDD;&#x4E2D;&#x6536;&#x5230;&#x65B0;&#x6765;&#x7535;</li>
          <li>8-On Hold&#xFF1A;&#x5750;&#x5E2D;&#x4FDD;&#x6301;&#x5F53;&#x524D;&#x901A;&#x8BDD;</li>
          <li>9-Paused&#xFF1A;&#x5750;&#x5E2D;&#x88AB;&#x6682;&#x505C;&#x670D;&#x52A1;&#xFF0C;&#x4E0D;&#x63A5;&#x6536;&#x6765;&#x7535;&#x4E1A;&#x52A1;</li>
          <li>10-Warp-up time&#xFF1A;&#x5750;&#x5E2D;&#x5904;&#x4E8E;&#x4F11;&#x606F;&#x72B6;&#x6001;&#xFF0C;&#x4E0D;&#x63A5;&#x6536;&#x6765;&#x7535;&#x4E1A;&#x52A1;</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>

### 实际示例

**请求示例**

```text
POST /api/v0.0.1/queuestatus/query?token=813b621cfe8eecf445a2ce1f4a079ffe&type=json HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
{
	"queueid":"9998"
}
```

```text
POST /api/v0.0.1/queuestatus/query?token=813b621cfe8eecf445a2ce1f4a079ffe&type=xml HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
<?xml version="1.0" encoding="UTF-8" ?>
<xml>
	<queueid>9998</queueid>
</xml>
```

**响应示例**

```text
HTTP/1.1 200 OK
Access-control-allow-origin: *
Access-control-allow-methods: GET, POST, OPTIONS, PUT, DELETE
{
    "status": "Success",
    "queue": {
        "queuenumber": "9998",
        "queuestatus": {
            "members": [
                {
                    "agent": "102",
                    "agentstatus": "1"
                },
                {
                    "agent": "101",
                    "agentstatus": "6"
                },
                {
                    "agent": "6000",
                    "agentstatus": "1"
                }
            ],
            "callercount": 0
        }
    }
}
```



```text
HTTP/1.1 200 OK
Access-control-allow-origin: *
Access-control-allow-methods: GET, POST, OPTIONS, PUT, DELETE
<?xml version="1.0" encoding="utf-8"?>
<xml>
	<status>Success</status>
	<queue>
		<queuenumber>9998</queuenumber>
		<queuestatus>
			<members>
				<item id="0">
					<agent>102</agent>
					<agentstatus>1</agentstatus>
				</item>
				<item id="1">
					<agent>101</agent>
					<agentstatus>5</agentstatus>
				</item>
				<item id="2">
					<agent>6000</agent>
					<agentstatus>1</agentstatus>
				</item>
			</members>
			<callercount>0</callercount>
		</queuestatus>
	</queue>
</xml>
```

