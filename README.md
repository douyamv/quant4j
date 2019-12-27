## 说明
 代码有点老 有时间会继续更新，优化的。有好的建议和需求可以发issue 能实现的 会在新的版本里加上。新版本会加上合约的交易 有好的建议欢迎提出来一起交流。-20191013

## 功能
 主要用于创建和管理自己的机器人,后台动态查看运行状态和收益信息。 最好的时候一天百分之3的收益. 别问什么策略,问就是低买高卖（滑稽脸）。
 我的实践是 多几个账号 多几个机器人 不同策略一起跑 掉价了别卖 等他涨 只要有波动就是赚。
```
 - 买入 / 卖出

- 策略中心
  - 简单策略
  - 指标策略
  - 策略列表

- 指标策略
  - 策略自定义添加
  - 策略回测（不完善）
  - 新增策略组
  - 修改策略组

- 简单策略
  - 各因子组合
  - 修改组合

- 托管中心
  - 添加机器人
  - 修改机器人
  - 查看机器人信息
  - 查看机器人下的订单信息
  - 查看机器人的盈利信息

- 配置中心
  - 火币api设置
  - 邮件提醒设置 下单后将推送邮件


```

## 开发

```bash
#后端
 springboot 咋启动？run main！

- [sql脚本](https://github.com/tokenIsme/images/blob/master/quant.sql)
- [前端ui](https://github.com/tokenIsme/quant-admin)

# 进入前端项目目录
cd quant-admin

# 安装依赖
npm install

# 建议不要直接使用 cnpm 安装依赖，会有各种诡异的 bug。可以通过如下操作解决 npm 下载速度慢的问题
npm install --registry=https://registry.npm.taobao.org

# 启动服务
npm run dev   
浏览器访问 http://124.156.120.130:9527


#后端
 - 后台由一个admin 控制中心 client 机器人运行节点 和一个注册中心管理 节点信息组成
   - 启动机器人由admin分发信息给相应的机器人节点，redis作为消息中间件，在client和admin之间传递信息。
   - 项目由springboot构建 运行admin,client,register三个项目 动态扩展的是client节点。
   - 进入admin模块配置好配置文件,run AdminApplication
   - 进入client模块配置好配置文件,这里主要配置的是redis和节点的外网ip和端口,以便让admin获取到节点的信息。 执行run ClientApplication
   - 进入register模块配置好配置文件,run RegisterApplication
```


## 图片展示

 ![image](https://github.com/tokenIsme/images/blob/master/1557888795(1).jpg)
 
 ![image](https://github.com/tokenIsme/images/blob/master/1557888642(1).jpg)
 
 ![image](https://github.com/tokenIsme/images/blob/master/1557888658(1).jpg)
 
 - 组合自定义的指标 例如选择rsi 然后选择14 或者其他的天数 来源可以选开盘价闭盘价最高价最低价 这四种价格的选择 买入或者是卖出
 ![image](https://github.com/tokenIsme/images/blob/master/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE(7).png)
 
 - 收益信息显示
 ![image](https://github.com/tokenIsme/images/blob/master/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE(6).png)

 ![image](https://github.com/tokenIsme/images/blob/master/1557888693(1).jpg)
 
 ![image](https://github.com/tokenIsme/images/blob/master/1557888732(1).jpg)
 
 
 ![image](https://github.com/tokenIsme/images/blob/master/1557888747(1).jpg)


## 其它
 
  - qt量化交易java版本目前只支持火币的所有币币交易，请自备翻墙代理或者香港新加坡日本的服务器

  - qt-admin 量化控制中心 qt-client 机器人节点 支持动态添加节点

  - 当前支持指标组合策略 可自由组合成金叉死叉等指标策略

## Donate

如果你觉得这个项目帮助到了你，你可以帮作者点个star表示鼓励 :tropical_drink:

## 说明：
 
  - 该项目为个人学习用,项目不完善，切勿作为公司线上产品，个人出现亏损问题，请自己负责哦！
  - 小赌怡情大赌伤身


