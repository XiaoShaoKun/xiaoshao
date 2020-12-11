---
description: 查询已创建的广播组。
---

# 查询广播组列表

### 请求地址

```text
POST /api/v0.0.1/paginggroup/lists?token={token}&type={type}
```

### 请求参数

无参数，直接发送查询广播组列表的请求即可。

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
    <tr>
      <td style="text-align:left">paginggrouplist</td>
      <td style="text-align:left">Array &lt;PaginggroupInfo&gt;</td>
      <td style="text-align:left">&#x5E7F;&#x64AD;&#x7EC4;&#x4FE1;&#x606F;&#x5217;&#x8868;&#x3002;</td>
    </tr>
  </tbody>
</table>

PaginggroupInfo

| 参数 | 类型 | 描述 |
| :--- | :--- | :--- |
| number | String | 广播组号码。 |
| name | String | 广播组名称。 |

### 示例

**请求示例**

```text
POST /api/v0.0.1/paginggrouplist/lists?token=277ac400357b509b4a587ff2157f7ad5
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
```

**响应示例**

```text
HTTP/1.1 200 OK
Server: Boa/0.94.14rc21
Accept-Ranges: bytes
Connection: close
Content-Type: application/json
Access-control-allow-origin: *
Access-control-allow-methods: GET, POST, OPTIONS, PUT, DELETE

{
    "status": "Success",
    "paginggrouplist": [
        {
            "number": "8891",
            "name": "test_api_paging_4"
        }
    ]
}
```

