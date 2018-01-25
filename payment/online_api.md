<p align="center">
<h3 align="center">MyPay —— 线上支付API</h3><hr>
</p>

```
这边提供的线上支付的API，返回一个可以供扫码的二维码字符串。
商户不需要进行额外太多开发，可异步返回。
异步的参数需要通过后台设置
```


#### 请求:

```
Method: HTTP POST

https://mypay.iemoney.co.nz/api/payment
```

|Parameter	|Type 	 |Description|
|-----------|--------|-----------|
|mid        |int     |5位数，这边获取注册|
|fee        |string  |最多两位小数的数值，如：200.65|
|trade_no   |string  |商户自己的订单号，32位，官方建议：时间日期，加随机数，唯一订单号|
|subject    |string  |商品描述|
|sign       |string  |签名，签名规则 sign md5($mid.$subject.$fee.$trade_no.$api_key)<br/>api_key 通过平台注册时获取|
|type       |string  |wechat, alipay|
|currency   |string  |可选参数，微信支付的时候，可以选择 CNY，默认是NZD|

#### 返回:

```
 {
    "is_success": "TRUE",
    "message": "https://qr.alipay.com/bax00275prqdpoca7m8c8090",
    "extra": []
 }
  
 {
    "is_success": "TRUE",
    "message": "weixin://wxpay/bizpayurl?pr=uD61Ba3",
    "extra": []
 }
```

#### 支付回调：

```
根据后台配置的支付类型，返回的对应的callback url
https://callback.url/?trade_no=20180125033932&status=SUCCESS&trade_status=SUCCES&sign=04a05e0d54598ef01882c18da7992762
```
