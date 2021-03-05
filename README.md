## 特别声明:

- 本项目已不再维护。

- 本仓库发布的 Actions_smzdm 项目中涉及的任何解锁和解密分析脚本，仅用于测试和学习研究，禁止用于商业用途，不能保证其合法性，准确性，完整性和有效性，请根据情况自行判断.

- 本项目内所有资源文件，禁止任何公众号、自媒体进行任何形式的转载、发布。

- jiegto 对任何脚本问题概不负责，包括但不限于由任何脚本错误导致的任何损失或损害.

- 间接使用脚本的任何用户，包括但不限于建立 VPS 或在某些行为违反国家/地区法律或相关法规的情况下进行传播, jiegto 对于由此引起的任何隐私泄漏或其他后果概不负责.

- 请勿将 Actions_smzdm 项目的任何内容用于商业或非法目的，否则后果自负.

- 如果任何单位或个人认为该项目的脚本可能涉嫌侵犯其权利，则应及时通知并提供身份证明，所有权证明，我们将在收到认证文件后删除相关脚本.

- 任何以任何方式查看此项目的人或直接或间接使用该 Actions_smzdm 项目的任何脚本的使用者都应仔细阅读此声明。jiegto 保留随时更改或补充此免责声明的权利。一旦使用并复制了任何相关脚本或 Actions_smzdm 项目的规则，则视为您已接受此免责声明.

  **您必须在下载后的 24 小时内从计算机或手机中完全删除以上内容.** </br>

  > **_您使用或者复制了本仓库且本人制作的任何脚本，则视为`已接受`此声明，请仔细阅读_**

## 使用方式

**不再推荐使用 Fork 的方式同步代码**

**[建议使用 reposync 的方式进行同步代码，详细教程请点此查看](https://github.com/sazs34/MyActions/blob/master/backup/reposync.md)**

1. 使用 reposync 的方式进行同步代码

2. 点击 Settings -> Secrets -> 点击绿色按钮 (如无绿色按钮说明已激活。直接到第三步。)

3. 新增 new secret 并设置 Secrets:

4. 双击右上角自己仓库 Star 触发

5. [定时执行](##定时执行)

## 定时执行

1. 支持手动执行，具体在 Actions 中选中要执行的 Workflows 后再在右侧可以看到 Run workflow，点击即可运行 此 workflow。

2. 如果嫌上一步麻烦的，也可以直接点击一下 star，你会发现所有的 workflow 都已执行。

3. 如需修改执行时间自行修改`.github\workflows\`下面的 yaml 内的` cron:` 执行时间为国际标准时间 [时间转换](http://www.timebie.com/cn/universalbeijing.php) 分钟在前，小时在后，尽量提前半小时，因为触发和下载需要一定时间。

## Secrets 集合

### 什么值得买专用

| 名称           | 内容              | 说明                            |
| -------------- | ----------------- | ------------------------------- |
| `SMZDM_COOKIE` | 什么值得买 cookie | 什么值得买 cookie，详细请往下看 |
| `SMZDM_USER`   | 什么值得买账号    | 什么值得买账号                  |
| `SMZDM_PASS`   | 什么值得买密码    | 什么值得买密码                  |

##### 推送通知环境变量(目前提供`微信server酱`、`pushplus(推送加)`、`iOS Bark APP`、`telegram机器人`、`钉钉机器人`、`企业微信机器人`、`iGot`、`QQ酷推`等通知方式)

|       Name        |                                        归属                                         |  属性  | 说明                                                                                                                                                                                                                              |
| :---------------: | :---------------------------------------------------------------------------------: | :----: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
|    `PUSH_KEY`     |                                 微信 server 酱推送                                  | 非必须 | server 酱的微信通知[官方文档](http://sc.ftqq.com/3.version)，已兼容 [Server 酱·Turbo 版](https://sct.ftqq.com/)                                                                                                                   |
|    `BARK_PUSH`    | [BARK 推送](https://apps.apple.com/us/app/bark-customed-notifications/id1403753865) | 非必须 | IOS 用户下载 BARK 这个 APP,填写内容是 app 提供的`设备码`，例如：https://api.day.app/123 ，那么此处的设备码就是`123`，再不懂看 [这个图](icon/bark.jpg)（注：支持自建填完整链接即可）                                               |
|   `BARK_SOUND`    | [BARK 推送](https://apps.apple.com/us/app/bark-customed-notifications/id1403753865) | 非必须 | bark 推送声音设置，例如`choo`,具体值请在`bark`-`推送铃声`-`查看所有铃声`                                                                                                                                                          |
|  `TG_BOT_TOKEN`   |                                    telegram 推送                                    | 非必须 | tg 推送(需设备可连接外网),`TG_BOT_TOKEN`和`TG_USER_ID`两者必需,填写自己申请[@BotFather](https://t.me/BotFather)的 Token,如`10xxx4:AAFcqxxxxgER5uw` , [具体教程](./backUp/TG_PUSH.md)                                              |
|   `TG_USER_ID`    |                                    telegram 推送                                    | 非必须 | tg 推送(需设备可连接外网),`TG_BOT_TOKEN`和`TG_USER_ID`两者必需,填写[@getuseridbot](https://t.me/getuseridbot)中获取到的纯数字 ID, [具体教程](./backUp/TG_PUSH.md)                                                                 |
|  `DD_BOT_TOKEN`   |                                      钉钉推送                                       | 非必须 | 钉钉推送(`DD_BOT_TOKEN`和`DD_BOT_SECRET`两者必需)[官方文档](https://developers.dingtalk.com/document/app/custom-robot-access) ,只需`https://oapi.dingtalk.com/robot/send?access_token=XXX` 等于`=`符号后面的 XXX 即可             |
|  `DD_BOT_SECRET`  |                                      钉钉推送                                       | 非必须 | (`DD_BOT_TOKEN`和`DD_BOT_SECRET`两者必需) ,密钥，机器人安全设置页面，加签一栏下面显示的 SEC 开头的`SECXXXXXXXXXX`等字符 , 注:钉钉机器人安全设置只需勾选`加签`即可，其他选项不要勾选,再不懂看 [这个图](icon/DD_bot.png)            |
|    `QYWX_KEY`     |                                 企业微信机器人推送                                  | 非必须 | 密钥，企业微信推送 webhook 后面的 key [详见官方说明文档](https://work.weixin.qq.com/api/doc/90000/90136/91770)                                                                                                                    |
|     `QYWX_AM`     |                                企业微信应用消息推送                                 | 非必须 | corpid,corpsecret,touser,agentid,素材库图片 id [参考文档 1](http://note.youdao.com/s/HMiudGkb) [参考文档 2](http://note.youdao.com/noteshare?id=1a0c8aff284ad28cbd011b29b3ad0191)<br>素材库图片填 0 为图文消息, 填 1 为纯文本消息 |
|  `IGOT_PUSH_KEY`  |                                      iGot 推送                                      | 非必须 | iGot 聚合推送，支持多方式推送，确保消息可达。 [参考文档](https://wahao.github.io/Bark-MP-helper)                                                                                                                                  |
| `PUSH_PLUS_TOKEN` |                                    pushplus 推送                                    | 非必须 | 微信扫码登录后一对一推送或一对多推送下面的 token(您的 Token) [官方网站](http://pushplus.hxtrip.com/)                                                                                                                              |
| `PUSH_PLUS_USER`  |                                    pushplus 推送                                    | 非必须 | 一对多推送的“群组编码”（一对多推送下面->您的群组(如无则新建)->群组编码）注:(1、需订阅者扫描二维码 2、如果您是创建群组所属人，也需点击“查看二维码”扫描绑定，否则不能接受群组消息推送)，只填`PUSH_PLUS_TOKEN`默认为一对一推送       |
|  `TG_PROXY_HOST`  |                                 Telegram 代理的 IP                                  | 非必须 | 代理类型为 http。例子：http 代理 http://127.0.0.1:1080 则填写 127.0.0.1                                                                                                                                                           |
|  `TG_PROXY_PORT`  |                                 Telegram 代理的端口                                 | 非必须 | 例子：http 代理 http://127.0.0.1:1080 则填写 1080                                                                                                                                                                                 |
|  |

### 什么值得买 Cookie 获取

1. 电脑浏览器访问 https://zhiyou.smzdm.com/user/ 进行登录，如果登录后，不是该页面，则重新在浏览器中访问一次 https://zhiyou.smzdm.com/user/ 即可。

2. 打开开发者工具,在 Network 选项卡，刷新页面 ,然后选中 user ，在右侧的 Headers 标签里，将 Cookie 字段从 sess= 开始到结束，复制出来。

![](https://github.com/jiegto/Actions_smzdm/blob/main/backup/SMZDM_Cookie.jpg?raw=true)

## 签到脚本说明

1. 什么值得买的会员体系更新后，连续签到 30 天加 30 经验值的福利已经没有，每日签到只能获得 2 点经验值。以现在的会员升级体系，从 V5 升级到 V6，需要 1 万的经验值，依靠签到需要连续签到 13 年半。

2. 所以在原来签到的基础上，增加了每日完成一些任务的功能，这样每日基本上可以获得 120 左右的经验值。V5 升级到 V6，只需要 84 天。

3. 什么值得买执行任务时，对每次任务的时间间隔有一定的要求，过短的时间间隔可能会没有任何奖励。如果在短时间内并行发起大量请求的话，严重的情况会导致账号异常，需要修改密码。所以在每次执行任务时，都加入了 3 秒的休眠时间，这会导致脚本的执行时间需要非常长，差不多 1 分钟左右。请把脚本超时时间设置到最长，建议 2 分钟以上，以免因为超时被强制中断。

4. 什么值得买 Web 端和 App 端每日自动签到脚本，并且完成每日点击去购买 10 次、点值 5 次、点赞 5 次、收藏 5 次的任务。

更多信息请参考[这里](https://github.com/blackmatrix7/ios_rule_script/blob/master/script/smzdm/README.md)

## 鸣谢

[@blackmatrix7](https://github.com/blackmatrix7/ios_rule_script/tree/master/script/smzdm) - 什么值得买签到脚本

[@BlueskyClouds](https://github.com/BlueskyClouds/My-Actions) - Actions 实现签到和推送

[@sazs34](https://github.com/sazs34) - reposync 同步相关
