### 1. 接口描述
本接口（UpdateDeviceShadow）用于更新虚拟设备信息。

接口请求域名：`iotcloud.api.qcloud.com`

### 2. 输入参数

以下请求参数列表仅列出了接口请求参数，其它参数见 [公共请求参数](https://cloud.tencent.com/document/api/213/6976) 页面。

| 参数名称       | 必选   | 类型     | 描述                             |
| ---------- | ---- | ------ | ------------------------------ |
| productID  | 是    | String | 产品ID                           |
| deviceName | 是    | String | 设备名称。命名规则：[a-zA-Z0-9:_-]{1,48} |
| state      | 是    | String | 虚拟设备的状态，json格式，由desired结构组成    |
| version    | 是    | Long   | 当前版本号，需要和后台的version保持一致，才能更新成功 |

### 3. 输出参数

| 参数名称      | 类型       | 描述                                       |
| --------- | -------- | ---------------------------------------- |
| code      | Int      | 公共错误码。0 表示成功，其他值表示失败，详见 [公共错误码](https://cloud.tencent.com/document/product/634/12279) 页面。 |
| codeDesc  | String   | 返回码描述                                    |
| message   | String   | 模块错误信息描述，格式为 "（模块错误码）模块错误信息" 详见本页面的 [模块错误码](#module_error_info) |
| state     | Object   | 虚拟设备当前状态                                 |
| metadata  | Object   | 虚拟设备属性的元信息，包括创建时间或者最后修改时间                |
| timestamp | DateTime | 服务器返回时间                                  |
| version   | Long     | 当前虚拟设备的版本号                               |

### 4. 示例

输入
<pre>
  var oState = {"state": {"desired": {"color": "red"}}};
  var sState = encodeURIComponent(JSON.stringify(oState ));
  https://iotcloud.api.qcloud.com/index.php?Action=UpdateDeviceShadow
  &deviceName=apple
  &productID=ABCDE12345
  &state=${sState}
  &<<a href="https://cloud.tencent.com/document/api/213/6976">公共请求参数</a>>
</pre>

输出
```json
{
    "data":{
    	"payload":{
    		"state": {
        		"desired": {
            		"color": "red"
        		}
    		},
    		"metadata": {
        		"desired": {
            		"color": {
                		"timestamp": 1509092895971
            		}
        		}
    		},
    		"timestamp": 1509443636326,
    		"version": 5
    	}
    }
    "message": "",
    "codeDesc": "Success",
    "code": 0
}
```
<span id = "module_error_info"></span>
### 5. 模块错误信息

| 模块错误码 | 描述                         |
| ----- | -------------------------- |
| 5001  | 设备不存在                      |
| 5002  | State json 对象的层数超过了限制，最大为 6 层 |
| 5003  | State json 对象中包含非法节点        |
| 5004  | State json 对象格式非法           |
| 5005  | version 不匹配，需要与后台版本一致       |
| 5006  | State json 对象超过大小限制，最大为 64k  |
| 5100  | 内部服务器错误，请联系技术人员            |
| 5101  | 请求参数非法                     |

