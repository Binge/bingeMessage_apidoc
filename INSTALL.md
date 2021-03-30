# INSTALL 

### 发送安装信息

#### 基本信息

| 接口名称 | 当前版本 | 当前状态 | 接口地址 | 请求方式 | 返回格式 |
|---|---|---|---|---|---|
| 安装器 | v1.0 | 完成 | /install | POST | json |

#### 请求

##### Headers:

| 参数名称 | 是否必须 | 备注 |
|---|---|---|
| Content-Type | 是 |  Content-Type: application/json |
| X-HA-Key | 是 |  |

##### Body:

| 参数名称 | 类型 | 是否必须 | 备注 |
|---|---|---|---|
| time | string | 是 | 当前时间，格式是时间戳，毫秒级 |
| timezone | string | 是 | 当前时区 |
| devicetype | string | 是 | 设备类型，iOS, Android, macOS, windows |
| devicetoken | string | 否 | iOS/macOS 设备必须填写 |
| deviceid | string | 否 | Android 设备必须填写  |

#### 返回

| 名称 | 类型 | 是否必须 | 备注 |
|---|---|---|---|
| code | int | 是 | 0，1 |
| msg | string | 是 | 成功，不成功 |
| data | string | 是 | null |

