SSL证书续费操作相当于在控制台重新申请了一个新证书，用户需重新安装部署到服务器上。新证书不影响现有证书的正常使用。
### 1.续费优势
证书续费与重新购买相比，有以下优势：    
1.1 **简化续费流程**。用户无需重新填写申请信息，系统自动拉取原有证书申请资料，确认后直接进入付款流程。付款成功后，添加生成的解析记录值，等待证书审核。   
1.2 **续费证书时效**。对于续费新证书，除正常续费时长外，原证书未用完的时间会增补到新证书里面，并会额外获得1-90天不等的赠送时长。客户不会因续费造成证书使用时间上的损失。   
    
### 2.证书续费流程
#### 2.1 进入证书续费入口
DV付费证书在过期前3个月会开启证书快速续费通道，在【状态】项中点击“快速续费”，弹出SSL证书续费提示，信息确认后，点击【前往付费】。    
![](https://mc.qcloudimg.com/static/img/d6555ae3c172ed86f2ebe3e59c600ff7/1.png)   
![](https://mc.qcloudimg.com/static/img/4e836183f65efca6d3f33975b297d9c6/2.png)   
#### 2.2 续费信息确认与支付
证书续费无需再次填写信息，由于证书续费后会生成一个新证书，因此要为新证书设置CSR文件。系统可自动生成CSR文件，用户也可以自己上传CSR文件。
用户在确认信息后，点击【快速支付】进入证书支付流程。如信息需要变更，请重新申请证书。
![](https://mc.qcloudimg.com/static/img/25feed97032dec3dd6848de63c14f39e/3.png)   
确认证书信息后，点击【确认购买】进行付款。   
![](https://mc.qcloudimg.com/static/img/b7f7bfa086caad55beb016b6753de6e2/5.png)  
#### 2.3 上传确认函并等待审核
购买成功后，会在证书管理控制台的证书列表中生成一个新的证书，状态为“待验证”，点击【详情】进入证书详情页。   
![](https://mc.qcloudimg.com/static/img/5e042746658b3c8e2158d065f890ee8f/6.png)    
证书详情中会生成解析验证值，您需要添加该条DNS解析记录。记录添加完成后，等待CA机构扫描验证，验证审核通过后会立即颁发证书。    
![](https://mc.qcloudimg.com/static/img/772a862270a42e29357e08b18f4c125d/4.png)

