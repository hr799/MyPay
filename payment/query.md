<p align="center">
<h3 align="center">MyPay —— 统一查询接口</h3><hr>
</p>

```
通过传递订单号和商户id查询订单状态
```


#### 请求:

```
Method: HTTP GET

https://mypay.iemoney.co.nz/api/check?mid=10209&trade_no=20180125053131486516729354003179&type=1&sign=xxxxxx
```

|Parameter	|Type 	 |Description|
|-----------|--------|-----------|
|mid        |int     |5位数，这边获取注册|
|trade_no   |string  |商户自己的订单号，32位，官方建议：时间日期，加随机数，唯一订单号|
|type       |int     |0.线下支付宝 1:线上支付宝，2:微信|
|sign       |string  |签名，签名规则 sign md5($mid.$trade_no.$type.$api_key)<br/>api_key 通过平台注册时获取|

#### 返回:

```
success:
	{
	    "is_success": "TRUE",
	    "message": "SUCCESS",
	    "extra": []
	}

fail:
	{
	    "is_success": "FALSE",
	    "message": "ERROR_RETURN",
	    "extra": []
	}
```
