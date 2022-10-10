# API接口说明文档

## 登录

### URL

- cs: `POST` http://api.aaa.com/login


描述：登录

ContentType：`application/x-www-form-urlencoded;charset=utf-8`

### 请求参数

#### Query Parameter

| 名称 | 类型 | 必填 | 最大长度 | 描述 | 示例值 |
| --- | --- | --- | --- | --- | --- |
| account | string | 否 | - | 用户登录名 | ac50wb |
| password | string | 否 | - | 用户密码 | wnxtt0 |

### 响应参数

| 名称 | 类型 | 必填 | 最大长度 | 描述 | 示例值 |
| --- | --- | --- | --- | --- | --- |
| message | string | 否 | - | 信息(一般错误信息才使用) | success |
| messageCode | string | 否 | - | 信息状态码 | 95366 |
| resultCode | string | 否 | - | 结果状态码(必须有值) | 95366 |
| data | object | 否 | - | 数据 |  |
| isSuccess | boolean | 否 | - | 是否成功 | true |

### 响应示例

```
{
    "message": "success",
    "messageCode": "95366",
    "resultCode": "95366",
    "data": {},
    "isSuccess": true
}
```

### 错误码

无

