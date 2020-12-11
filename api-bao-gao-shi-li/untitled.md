---
description: 当 PBX 系统启动后，PBX 会向应用服务器推送该报告。
---

# 系统启动报告

注： 前提条件：应用服务端已连接上 API 服务器，并且完成认证。



### 报告参数

| 名称 | 类型 | 描述 |
| :--- | :--- | :--- |
| `action` | String | 启动系统事件。 |
| `sn` | String | PBX 的 SN 码。 |

### 报告示例

```text
POST / HTTP/1.1
User-Agent: WebAPI
Host: 172.16.6.150: 8260
Content-Type: application/json
Accept: application/json
{
    "action": "BootUp",
    "sn": "369351034049"
}
```



