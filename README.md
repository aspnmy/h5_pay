# h5_pay
订阅号跨号支付及全网通用支付业务
微新移动商学院

春秋老怪 18857165066 aspnmy@aodao.com.cn

https://wx.aodao.com.cn
跨号支付：使订阅号可以通过服务号完成收款，即保留每日一条的高频能力，也可以完成支付收款

1.1纯微信能力，订阅号需和服务号在一个域下，纯微信端支付

1.2通用能力，订阅号不和服务号在同一域下，支持全通道支付，即pc，手机浏览器，QQ内都可支付。


1.3流程：

1.3.1微信端：用户进入订阅号收款界面，获取手机验证码验证注册服务号用户帐号，通过后进入付款界面，支持微信，支付宝，百度金融，银联四通道，完成支付。


1.3.2非微信端：直付模式同上

1.3.3二维码拼接模式，订阅号生成统一收款二维码，用户扫码完成后续流程，		可呼起微信支付，QQ钱包，支付宝APP等，苹果系统支持较差，安卓基本全通过。

拼接规则查看下面2小节


2.多产品多门店，优化下线收款场景

分销商城业务中完成扫街快速付款模式的一种探讨

2.1二维码静态模式

参数：


orderid 必传获取到openid.time=>orderid 

未获取openid ,username/mobile.time=>orderid

name 必传 
name的参数值有storid 	门店id
     goodsid 商品ID
goodsid 商品组ID 
groupid 商品分类ID
diyfrom 自定义页面ID

fee 必传 收款金额

ak 必传 贩卖机硬件必传值，无值传0

time time()方法取得服务器当前时间值

2.2接口模式:

data=urlencode(json_encode(orderid|name|fee|time))

URL：URL/?v=3&payid=data
v=1 明文模式
v=2 密钥签证模式
v=3	接口模式
ak ! = 0 贩卖机模式


2.3纯二维码模式：

URL：URL/?v=1&c=orderid&d=name&f=fee&ak=ak&t=time
c = orderid
d = name
f  = fee
ak  = ak
t  = time

生成二维码用户扫码即可呼起密码支付界面，简化2步，支付成功会增加指定项目的订单记录


2.4H5支付页面:

2.4.1.每个参数值均为动态值，用户从单个/多个商品下单按钮进入，自动传值，生成二维码或直接呼起API接口（推荐使用v=3模式）
orderid = {orderid}
name = {storid|goodsid|goodsid|groupid|diyfrom}
fee = {fee}
ak =AK
t=time()
模式：
v=1 明文模式
v=2 密钥签证模式
v=3	接口模式
ak ! = 0 贩卖机模式
2.4.2.每个参数值均为动态值，用户进入预设的H5页面，选择预设门店或商品组下商品ID，点支付直接呼起输密界面

2.4.3.贩卖机使用二维码传ak模式



本项目已经开源在本人Git上，欢迎社群补完

https://github.com/aspnmy/h5_pay





