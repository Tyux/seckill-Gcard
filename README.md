## 主要功能

- 登陆京东商城（[www.jd.com](http://www.jd.com/)）
  - 用京东APP扫码给出的二维码
- 预约茅台
  - 定时自动预约
- 秒杀预约后等待抢购
  - 定时开始自动抢购

## 运行环境
请安装大于等于python 3.6 的版本运行此项目
- [Python下载](https://www.python.org/)

## 第三方库

- 需要使用到的库已经放在requirements.txt，使用pip安装的可以使用指令  
`pip install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple/`


## 使用教程  
#### 1. 推荐Chrome浏览器
#### 2. 网页扫码登录，或者账号密码登录
#### 3. 填写config.ini配置信息
(1)`eid`和`fp`找个普通商品随便下单,然后抓包就能看到,这两个值可以填固定的
> 随便找一个商品下单，然后进入结算页面，打开浏览器的调试窗口，切换到控制台Tab页，在控制台中输入变量`_JdTdudfp`，即可从输出的Json中获取`eid`和`fp`。  
> 不会的话参考原作者的issue https://github.com/zhou-xiaojun/jd_mask/issues/22

(2)`sku_id`,`DEFAULT_USER_AGENT`
> `sku_id`已经按照茅台的填好。
> `cookies_string` 现在已经不需要填写了，扫码确认登陆后会自动生成cookie信息
> `DEFAULT_USER_AGENT` 可以用默认的，无需修改

(3)误差时间`step_error_time_ms`调整
> 根据控制台打印的信息手动修改一下，【900】是多少就填写多少
- 正在等待到达设定时间:2021-01-07 09:59:59.800000，检测本地时间与京东服务器时间误差为【1】毫秒


以上都是必须的.
> tips：
> 在程序开始运行后，会检测本地时间与京东服务器时间，输出的差值为本地时间-京东服务器时间，即-50为本地时间比京东服务器时间慢50ms。
> 本代码的执行的抢购时间以本地电脑/服务器时间为准


#### 4.运行main.py
根据提示选择相应功能即可

#### 5.抢购结果确认
抢购是否成功通常在程序开始的一分钟内可见分晓！  
搜索日志，出现“抢购成功，订单号xxxxx"，代表成功抢到了，务必半小时内支付订单！程序暂时不支持自动停止，需要手动STOP！  
若两分钟还未抢购成功，基本上就是没抢到！程序暂时不支持自动停止，需要手动STOP！  


## 感谢
##### 感谢原作者的无私奉献 https://github.com/ChinaVolvocars/jd_maotai_seckill
##### 非常感谢原作者 https://github.com/zhou-xiaojun/jd_mask 提供的代码
##### 也非常感谢 https://github.com/wlwwu/jd_maotai 进行的优化
