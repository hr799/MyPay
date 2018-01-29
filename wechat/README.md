<p align="center">
<h3 align="center">MyPay —— 微信支付API</h3><hr>
</p>

```
适用于商户自己的微信端电商平台的支付
移动端微信支付的网页，商户不需要进行额外太多开发，可同步返回和异步返回。
同步返回和异步的参数需要通过后台设置，返回参数同上接口
```


#### 请求:

```
Method: HTTP GET

https://mypay.iemoney.co.nz/wechatApi/wechatPay/$mid/$fee/$trade_no/$memo
```

|Parameter	|Type 	 |Description|
|-----------|--------|-----------|
|mid        |int     |5位数，这边获取注册|
|fee        |string  |最多两位小数的数值，如：200.65|
|trade_no   |string  |商户自己的订单号，32位，官方建议：时间日期，加随机数，唯一订单号|
|subject    |string  |订单留言|

#### 返回:

```

同步返回：
https://return.url/?trade_no=20180125033932&status=SUCCESS

异步返回：
https://callback.url/?trade_no=20180125033932&status=SUCCESS

```
