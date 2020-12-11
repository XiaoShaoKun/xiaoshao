# 退出登录

注： 请求示例中的 token 为API 登录时返回的 token。



### Endpoint

```text
POST /api/v0.0.1/logout?token={token}
```

### 请求参数

无参数，直接发送退出登录的请求即可。

### 实际示例

**请求示例**

```text
POST /api/v0.0.1/logout?token=813b621cfe8eecf445a2ce1f4a079ffe HTTP/1.1 HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
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

