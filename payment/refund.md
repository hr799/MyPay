<p align="center">
<h3 align="center">MyPay —— 退款接口</h3><hr>
</p>

```
这边提供的退款接口，只能当天退款，避免财务结算后的流程问题，隔天，或者几天后退款的，需要提交工单，手动退款。
通过平台退款的，没有手续费的成本。
```


#### 请求:

```
Method: HTTP POST

https://mypay.iemoney.co.nz/api/refund
```

|Parameter	|Type 	 |Description|
|-----------|--------|-----------|
|mid        |int     |5位数，这边获取注册|
|refund_fee |string  |最多两位小数的数值，如：200.65|
|trade_no   |string  |商户自己的订单号，32位，官方建议：时间日期，加随机数，唯一订单号|
|type       |int     |0.线下支付宝 1:线上支付宝，2:微信|
|sign       |string  |签名，签名规则 sign md5($mid.$refund_fee.$trade_no.$api_key)<br/>api_key 通过平台注册时获取|

#### 返回:

```
 {
    "is_success": "TRUE",
    "message": "SUCCESS",
    "extra": []
 }
 
```


