### 1. 接口描述

本接口（DeleteProduct）用于删除一个物联云产品。

接口请求域名：`iotcloud.api.qcloud.com`

### 2. 输入参数

以下请求参数列表仅列出了接口请求参数，其它参数见 [公共请求参数](https://cloud.tencent.com/document/api/213/6976) 页面。

| 参数名称      | 必选   | 类型     | 描述        |
| --------- | ---- | ------ | --------- |
| productID | 是    | String | 需要删除的产品 ID |


### 3. 输出参数

| 参数名称     | 类型     | 描述                                       |
| -------- | ------ | ---------------------------------------- |
| code     | Int    | 公共错误码。0 表示成功，其他值表示失败，详见 [公共错误码](https://cloud.tencent.com/document/product/634/12279) 页面 |
| message  | String | 模块错误信息描述，格式为 "（模块错误码）模块错误信息" ，详见本页面的 [模块错误码](#module_error_info) |
| codeDesc | String | 模块错误码的英文描述                               |

### 4. 示例

输入
<pre>
  https://iotcloud.api.qcloud.com/index.php?Action=DeleteProduct
  &productID=ABCDE12345
  &<<a href="https://cloud.tencent.com/document/api/213/6976">公共请求参数</a>>
</pre>

输出
```
{
    "message": "",
    "codeDesc": "Success",
    "code": 0
}
```
<span id = "module_error_info"></span>
### 5. 模块错误码

| 模块错误码 | 描述              |
| ----- | --------------- |
| 1004  | 删除的产品不存在        |
| 1005  | 删除的产品下还包括未删除的设备 |
| 1100  | 内部服务器错误，请联系技术人员 |
| 1101  | 请求参数非法          |
