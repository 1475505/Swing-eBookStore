# Report

---

### 需求分析

设计一个贩卖各类书籍的电子商务网站的购物车系统。具备GUI。

- 对所有的教材类图书实行每本一元的折扣；
- 对连环画类图书提供每本7%的促销折扣；
- 而对非教材类的计算机图书有3%的折扣；
- 对其余书没有折扣。

#### 实现的功能

- 基于订单的购物车信息显示、折扣价格计算。
- 允许对新增加的书籍进行折扣配置（不影响已添加的书籍）

### 软件内容

#### 开发环境

使用 Windows 11操作系统，IDE：IntelliJ IDEA 2022.1。使用的JDK版本是1.8。

#### 类图

![](http://img.070077.xyz//image-20220704185619953.png)

#### 执行流

![](http://img.070077.xyz//image-20220704143251776.png)

#### 细节规约

1. 如果某个订单图书的折扣后价格小于0，不会倒贴钱，而是会默认价格为0，过度的折扣将被忽略。
2. 每次修改策略，仅对新增加的订单书籍生效，对已添加到购物车的订单不受影响。策略当前显示的值就是当前的配置值。

### 测试用例

一次购物，购买了2本教材类图书《UML与模式应用》，单价是18元/本；购买了2本非教材类的计算机图书《Java与模式》，单价是34元/本；购买了1本非教材类的计算机图书《HeadFirst 设计模式》，单价是58元/本；购买了3本连环画类图书《爱丽丝历险记》，单价是30元/本；购买了1本其他类图书《煲汤大全》，单价是20元/本。请计算出本次购物优惠后价格。

![](http://img.070077.xyz//image-20220704141842071.png)

#### 界面解释

点击创建订单，可以增加对应的书籍信息和订单属性，确认后会自动计算折扣后价格，增加到购物车中，购物车信息会实时更新。

![](http://img.070077.xyz//image-20220704185848438.png)

点击结束订单后，将清空本次数据、购物车。不过此时的策略不会恢复成默认值。

![](http://img.070077.xyz//image-20220704191414084.png)
