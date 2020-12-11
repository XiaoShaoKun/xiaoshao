---
description: 当分机状态发生变更时，PBX 主动向应用服务器推送变更信息。
---

# 分机状态变更报告

注： 你需要提前在 PBX 的二次开发接口 配置页面勾选分机的状态监控。



### 分机状态

* **响铃 \(Ringing\)**：当分机有来电正在响铃时，PBX 会向应用服务器推送该报告。
* **忙 \(InUse\)**：当分机摘机时，PBX 会向应用服务器推送该报告。注： 分机由空闲状态或响铃状态摘机后则分机的状态变为 InUse 状态。
* **空闲 \(Idle\)**：当分机由忙碌变成空闲时，PBX 会向应用服务器推送该报告。
* **已注册 \(Registered\)**：当 IP 分机由未注册变为注册上时，或者当 IP 分机的地址变更时，PBX 会向应用服务器推送该报告。
* **未注册 \(Unregistered\)**：当 IP 分机由注册上变为未注册时，PBX 会向应用服务器推送该报告。

### 报告参数

| 名称 | 类型 | 描述 |
| :--- | :--- | :--- |
| `action` | String | 分机状态变更事件。 |
| `extension` | Int | 状态变更的分机号。 |
| `status` | String | 变更后的状态。 |
| `sn` | String | PBX 的 SN 码。 |

### 报告示例

```text
POST  HTTP/1.1
Host:172.16.6.150
Content-Length:83
Accept: application/json
Content-Type:application/json
Connection:close

{
    "action":"ExtensionStatus",
    "extension":"101",
    "status":"InUse",
    "sn":"a09805021987"
}
```

