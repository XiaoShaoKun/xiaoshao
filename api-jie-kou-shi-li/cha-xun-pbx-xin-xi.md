# 查询 PBX 信息



### Endpoint

```text
POST /api/v0.0.1/deviceinfo/query?token={token}&type={type}
```

### 请求参数

无参数，直接发送查询设备信息的请求即可。

### 响应参数

| 名称 | 类型 | 描述 |
| :--- | :--- | :--- |
| `devicename` | String | 产品设备名称。 |
| `sn` | String | 产品序列号。 |
| `hardwarever` | String | 硬件版本号。 |
| `firmwarever` | String | 固件版本号。 |
| `systemtime` | String | 系统时间。 |
| `uptime` | String | 启动时间。 |
| `extensionstatus` | String | 当前分机数/总分机数。 |

### 实际示例

**请求示例**

```text
POST /api/v1.1.0/deviceinfo/query?token=277ac400357b509b4a587ff2157f7ad5&type=json HTTP/1.1 HTTP/1.1
Content-Type:application/json; charset=utf-8
Host: 172.16.6.150
```

```text
POST /api/v1.1.0/deviceinfo/query?token=277ac400357b509b4a587ff2157f7ad5&type=xml HTTP/1.1 HTTP/1.1
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
    "deviceinfo": {
        "devicename": "UC501",
        "sn": "a09805021987",
        "hardwarever": "3.1",
        "firmwarever": "4.1.1",
        "systemtime": "2020-05-19 04:06:07",
        "uptime": "2020-Mar-23-08:33:22",
        "extensionstatus": "21/300"
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
    <deviceinfo>
        <devicename>UC501</devicename>
        <sn>a09805021987</sn>
        <hardwarever>3.1</hardwarever>
        <firmwarever>4.1.1</firmwarever>
        <systemtime>2020-05-22 07:24:00</systemtime>
        <uptime>2020-Mar-23-08:33:22</uptime>
        <extensionstatus>21/300</extensionstatus>
    </deviceinfo>
</xml>
```



