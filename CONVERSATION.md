# 对话 

### 创建对话 

#### 基本信息

| 接口名称 | 当前版本 | 当前状态 | 接口地址 | 请求方式 | 返回格式 |
|---|---|---|---|---|---|
| 创建对话 | v1.0 | 完成 | /conversation | POST | json |

#### 请求

##### Headers:

| 参数名称 | 是否必须 | 备注 |
|---|---|---|
| Content-Type | 是 | Content-Type: application/json |
| X-HA-Key | 是 |  |
| X-HA-Session | 是 | 当前登录用户的 session |

##### Body:

| 参数名称 | 类型 | 是否必须 | 备注 |
|---|---|---|---|
| passiveuser | int | 是 | 参与对话的用户 UID |
| time | string | 是 | 当前时间，格式是时间戳，毫秒级 |

#### 返回

| 名称 | 类型 | 是否必须 | 备注 |
|---|---|---|---|
| code | int | 是 | 0，1 |
| msg | string | 是 | 成功，不成功 |
| data | object | 是 | 返回 |

##### data

| 名称 | 类型 | 是否必须 | 备注 |
|---|---|---|---|
| conversationid | int | 是 | 该对话的 ID，负数，九个数字 |
| match | array | 是 | 对话的两个人的 ID，格式为 ["123456","654321"] |

---

### 发送信息

#### 基本信息

| 接口名称 | 当前版本 | 当前状态 | 接口地址 | 请求方式 | 返回格式 |
|---|---|---|---|---|---|
| 发送信息 | v1.0 | 完成 | /message| POST | json |

#### 请求

##### Headers:

| 参数名称 | 是否必须 | 备注 |
|---|---|---|
| Content-Type | 是 | Content-Type: application/json |
| X-APP-Key | 是 |  |
| X-APP-Session | 是 | 当前登录用户的 session |

##### Body:

| 参数名称 | 类型 | 是否必须 | 备注 |
|---|---|---|---|
| conversationid | int | 是 | 对话的 ID，负数，九个数字 |
| type | int | 是 | 信息的类型，-1 文本，-2 图像， -3 视频， -4 文件， -5 位置， -6 音频|
| content | string | 是 | 信息内容，如果是图像，视频，音频，文件，则使用 url |
| time | string | 是 | 当前时间，格式是时间戳，毫秒级 |

#### 返回

| 名称 | 类型 | 是否必须 | 备注 |
|---|---|---|---|
| code | int | 是 | 0，1 |
| msg | string | 是 | 成功，不成功 |
| data | object | 是 | 返回内容，数组格式 |

##### data

| 名称 | 类型 | 是否必须 | 备注 |
|---|---|---|---|
| issent | int | 是 | 是否已发送 |
| ispushed | int | 是 | 是否已推送 |
| isread | int | 是 | 是否已阅读|

---

### 某组对话内容列表 

#### 基本信息

| 接口名称 | 当前版本 | 当前状态 | 接口地址 | 请求方式 | 返回格式 |
|---|---|---|---|---|---|
| 某组对话内容列表 | v1.0 | 完成 | /message | GET | json |

#### 请求

##### Headers:

| 参数名称 | 是否必须 | 备注 |
|---|---|---|
| Content-Type | 是 | Content-Type: application/json |
| X-APP-Key | 是 |  |
| X-APP-Session | 是 | 当前登录用户的 session |

##### URL:

| 参数名称 | 类型 | 是否必须 | 备注 |
|---|---|---|---|
| conversationid | int | 是 | 对话的 ID，负数，九个数字 |
| start | int | 否 | 从第几条开始，默认 0 |
| limit | int | 否 | 每页显示的条数，默认 20 |

#### 返回

| 名称 | 类型 | 是否必须 | 备注 |
|---|---|---|---|
| code | int | 是 | 0，1 |
| msg | string | 是 | 成功，不成功 |
| data | array | 是 | 返回改组对话的所有内容 |

##### data

| 名称 | 类型 | 是否必须 | 备注 |
|---|---|---|---|
| id | int | 是 | 用户的 ID |
| username | string | 是 | 用户名，可 @ 部分 |
| nickname | string | 是 | 昵称 |
| avatar | string | 是 | 头像地址 |
| time | string | 是 | 信息发送时间 |

---

### 删除信息

#### 基本信息

| 接口名称 | 当前版本 | 当前状态 | 接口地址 | 请求方式 | 返回格式 |
|---|---|---|---|---|---|
| 删除信息 | v1.0 | 完成 | /message| DELETE | json |

#### 请求

##### Headers:

| 参数名称 | 是否必须 | 备注 |
|---|---|---|
| Content-Type | 是 | Content-Type: application/json |
| X-APP-Key | 是 |  |
| X-APP-Session | 是 | 当前登录用户的 session |

##### Body:

| 参数名称 | 类型 | 是否必须 | 备注 |
|---|---|---|---|
| messagekey | string | 是 | 待删除的信息的 key |
| type | int | 是 | 1 仅自己，2 群体 |

#### 返回

| 名称 | 类型 | 是否必须 | 备注 |
|---|---|---|---|
| code | int | 是 | 0，1 |
| msg | string | 是 | 成功，不成功 |
| data | string | 是 | null |

