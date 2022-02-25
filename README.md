### 项目介绍
本项目是一个在群里可以通知打cf的机器人项目，以及通知或者查询其他比赛的通知机器人，如果您觉得项目写的不错可以点一下右上角的✨`Star`，谢谢啦


### 功能介绍
目前实现的功能有：
* 查询CF比赛
* 查询对应id的cf分数
* 查询AtCoder比赛
* 查询AtCoder对应id的ratting分数
* 查询力扣的比赛
* 查询牛客比赛
* 随机qcjj->随机发送清楚姐姐图片
* CF上下号提醒
* 市级城市的天气查询
* ....

还在计划中的功能：
* 通过qq添加qcjj图片
* ...

### 接口调用
本项目基于Python3.8.10为主要开发版本，以[YiriMirai](https://github.com/YiriMiraiProject/YiriMirai)为主要依赖库

### 部署方法

1. 环境配置
   * 请参照YiriMirai的教程环境配置：https://yiri-mirai.wybxc.cc/tutorials/01/configuration
2. 使用Mirai登陆qq（如果是linux服务器，参照官网教程，如何挂起而不退出：https://yiri-mirai.wybxc.cc/tutorials/02/linux）
3. clone到本地或者服务器中
~~~shell
git clone git@github.com:INGg/ACM_Contest_QQbot.git
~~~
3. 修改`main.py`中bot的qq号为你自己的qq号
~~~python
bot = Mirai(
        qq=*****,  # 改成你的机器人的 QQ 号
        adapter=WebSocketAdapter(
            verify_key='yirimirai', host='localhost', port=8080
        )
    )
    hdc = HandlerControl(bot)  # 事件接收器
~~~
4. 安装对应的库
~~~shell
pip3 install httpx
pip3 install yiri-mirai
pip3 install python-dateutil
pip3 install yiri-mirai-trigger
pip3 install requests
pip3 install lxml
pip3 install apscheduler
# 应该是全了qwq，如果不全请根据报错来安装相应的包，如果方便请您告知我，我将更新安装命令
~~~

5. 启动bot
~~~shell
python3 main.py
# 或 python main.py
~~~

***
注：在`main.py`中，函数`async def notify_contest_info():`中的qq号请改成你想要通知的个人或群组