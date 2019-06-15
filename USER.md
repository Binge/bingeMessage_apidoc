# 用户信息

### 用户信息

#### 基本信息

| 接口名称 | 当前版本 | 当前状态 | 接口地址 | 请求方式 | 返回格式 |
|---|---|---|---|---|---|
| 用户信息 | v1.0 | 完成 | /user | GET | json |

#### 请求

##### Headers:

| 参数名称 | 参考 | 是否必须 | 备注 |
|---|---|---|---|
| Content-Type | Content-Type: application/json | 是 |  |
| X-APP-Key | 123456 | 是 |  |
| X-APP-Session | 123456 | 是 | 当前登录用户的 session |

#### 返回

| 名称 | 类型 | 是否必须 | 备注 |
|---|---|---|---|
| code | int | 是 | 0，1 |
| msg | string | 是 | 成功，不成功 |
| data | array | 是 | 返回除密码之外的用户的所有信息，数组格式 |

##### data

| 名称 | 类型 | 是否必须 | 备注 |
|---|---|---|---|
| id | int | 是 | 0，1 |
| email | string | 是 | email |
| username | string | 是 | 用户名，可 @ 部分 |
| nickname | string | 是 | 昵称 |
| avatar | string | 是 | 头像地址 |

---

### 禁止用户

#### 基本信息

| 接口名称 | 当前版本 | 当前状态 | 接口地址 | 请求方式 | 返回格式 |
|---|---|---|---|---|---|
| 禁止用户 | v1.0 | 完成 | /user\_block | POST | json |

#### 请求

##### Headers:

| 参数名称 | 参考 | 是否必须 | 备注 |
|---|---|---|---|
| Content-Type | Content-Type: application/json | 是 |  |
| X-APP-Key | 123456 | 是 |  |
| X-APP-Session | 123456 | 是 | 当前登录用户的 session |

##### Body:

| 参数名称 | 参考 | 是否必须 | 备注 |
|---|---|---|---|
| passiveuser | 12345678 | 是 | 被禁止的用户 |
| time |  | 是 | 当前时间，格式是时间戳，毫秒级 |

#### 返回

| 名称 | 类型 | 是否必须 | 备注 |
|---|---|---|---|
| code | int | 是 | 0，1 |
| msg | string | 是 | 成功，不成功 |
| data | string | 是 | null |

---

### 举报用户

#### 基本信息

| 接口名称 | 当前版本 | 当前状态 | 接口地址 | 请求方式 | 返回格式 |
|---|---|---|---|---|---|
| 举报用户 | v1.0 | 完成 | /user\_report | POST | json |

#### 请求

##### Headers:

| 参数名称 | 参考 | 是否必须 | 备注 |
|---|---|---|---|
| Content-Type | Content-Type: application/json | 是 |  |
| X-APP-Key | 123456 | 是 |  |
| X-APP-Session | 123456 | 是 | 当前登录用户的 session |

##### Body:

| 参数名称 | 参考 | 是否必须 | 备注 |
|---|---|---|---|
| passiveuser | 12345678 | 是 | 被举报的用户 |
| time |  | 是 | 当前时间，格式是时间戳，毫秒级 |

#### 返回

| 名称 | 类型 | 是否必须 | 备注 |
|---|---|---|---|
| code | int | 是 | 0，1 |
| msg | string | 是 | 成功，不成功 |
| data | string | 是 | null |