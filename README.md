# 收集一些自用脚本...

# 使用教程

具体细节请进入脚本查看。

【拉库直连命令】 `ql repo https://github.com/asd920/Script.git`

【国内镜像】（选一个即可）:
`ql repo https://hub.fastgit.xyz/asd920/Script.git`

`ql repo https://hub.0z.gs/asd920/Script.git`

# 关于小号

建议：玩毛不要用自己常用手机，不然垃圾短信一堆

* 移动：和多号app（5元/月）
* 联通：沃小号app（5元/月）
* 联通&腾讯：微小号（小程序 10元/月）
* 联通&阿里：阿里小号app（已下线，续期的可以继续用）


# 在线请求头转JSON

我把我已知的都列举出来了，也欢迎投更好用的

* [uutool](https://uutool.cn/header2json/)

* [wejson](https://wejson.cn/header2json/)


### 咔咔 kaka.js

cron 35 9 * * * 一天一次

<details>
<summary>食用步骤：</summary>
<br />

* [x] 收益：填写邀请码（G1BD8MP）自动获得5元，每天提现1元到支付宝

* [x] 多账户：用@隔开

把任意api.imkaka.com捉包头里的Cookie(viewchat_access_token=xxxxxxxxx 这个)填到kakaCookie里

    export kakaCookie='viewchat_access_token=xxxxxxxxx'

</details>


### 卡夫享 kfx.js

cron 11 9 * * * 一天一次

<details>
<summary>食用步骤：</summary>
<br />

* [x] 收益：每天签到1积分，分享一次5积分(每月有上限)  20分换2京东E卡，100分换10元话费，200分换20元话费

* [x] 多账户：用@隔开

注册链接：https://fscrm.kraftheinz.net.cn/?from=G20W5cUuyQ0JR+ISSo7/Ag==

找fscrm.kraftheinz.net.cn的包，把header里的token填到变量kfxtoken里

    export kfxtoken='***'

</details>


### 酷狗大字版 kgdzb.js(安卓)

cron 0 9 * * * 看任务一天一次就可

<details>
<summary>食用步骤：</summary>
<br />

* [x] 收益：一天0.6  

* [x] 多账户：用@隔开

进APP-福利，抓get包，每个人抓的host可能不一致，找*.kugou.com，只要有token、userid等关键数据即可，把整段url，填入变量，参考 `https://gateway.kugou.com/v1/***`

    export kugouurl='这里填入url链接！链接！'


</details>


### 快手极速版 ksjsb.js (leaf版)

cron 38 7-22 * * * (每天15次)

<details>
<summary>食用步骤：</summary>
<br />
抓POST包，进入积分换好礼页面即可获取数据，只要有Cookie就行

https://api.kuaishouzt.com/rest/zt/appsupport/yoda/accelerate/info

把Cookie中的kuaishou.api_st复制出来，包括分号，多账号换行隔开

    export ksjsbCookie='kuaishou.api_st=***;'

默认每天0点自动兑换金币，15点提现，要改的话把提现时间填到变量，不想提现设置成99，提到微信把`ksPayType=WECHAT;`，提到支付宝把`ksPayType=ALIPAY;`，写到对应账号ck后面

    export ksjsbWithdrawTime='15'

默认从高到低提现，固定金额用以下变量。如提现失败，手动接验证码提现一次，自动检测绑定了微信还是支付宝提现账号，都绑定了的话默认提现到微信

    export ksjsbCash='100'

默认提现时间会触发通知，可以把ksjsbNotify设置成2，每次运行都通知；为0，则不通知

    export ksjsbNotify='0'

快手如果提示违规操作，无法体现，可以先暂停脚本，手动提现。

极速版入口：左上角三横-积分换好礼
  
</details>


### 快手 ks.js

cron 22 10-20 * * *

<details>
<summary>食用步骤：</summary>
<br />
普通版的快手，非极速版，CK可以通用

注意现在多一个did的设备参数，必填！多账户@隔开

> 由于我IOS端找不到入口，我就用的极速版抓的CK里提取了did数值，粘贴在后面，任务一样跑

    export ksCookie='kuaishou.api_st=***;did=***;'

默认每天0点自动兑换金币，14点提现，不想提现设置成99，提到微信把`ksPayType=WECHAT;`，提到支付宝把`ksPayType=ALIPAY;`，写到对应账号ck后面

    export ksWithdrawTime='14'

默认提现2块，要改的话把提现金额填到变量。如提现失败，手动接验证码提现一次，自动检测绑定了微信还是支付宝提现账号，都绑定了的话默认提现到微信

>手动提现入口：头像-更多-我的钱包-天降红包提现，默认从高到低提现，固定金额用以下变量

    export ksCash='100'

默认提现时间会触发通知，可以把ksjsbNotify设置成2，每次运行都通知；为0，则不通知

    export ksNotify='0'

</details>


### 康师傅畅饮社wx_ksfcys.js

cron 42 9,18 * * *

<details>
<summary>食用步骤：</summary>
<br />
微信小程序，注册送200积分

抓GET包，点我的即可获取数据，多账号@隔开

https://club.biqr.cn/api/member/getMemberInfo

    export ksfcysToken='***'

默认不会抽奖，如果需要50积分抽奖，请设置变量ksfcysDraw为true

    export ksfcysDraw="true"
  
    // 2022-3-2积分可换E卡，重进小程序有可能会挤掉线，请重新抓

</details>


### 九章头条 jztt.js

Cron 15 0,6-23 * * *

<details>
<summary>食用步骤：</summary>
<br />
抓get包，进app-任务，抓取token值

https://api.st615.com/v2/user/info

    export jzttToken="***"

自定义阅读次数，默认每次阅读3篇文章

    export jzttReadNum="***"

提现金额，按门槛自动提现，从大到小，默认顺序5元，2元和0.3元

    export jzttWithdrawLimit="***"

</details>

### 疯狂水晶 fksj.js

 cron 0 * * * *

<details>
<summary>食用步骤：</summary>
<br />

  下载地址: http://mmwk.mmwl.fun/download/9570691cce3dc93a?user=18172
    
 * 变量格式: export fksj_data='userid1 @ userid2'  多个账号用 @分割
 *
 * userid  小程序(疯狂水晶) app 页面都有

</details>

### 金砖旷工 jzkg.js

 cron 1 * * * *

<details>
<summary>食用步骤：</summary>
<br />

  下载地址: http://jzkg.jmsfx.top/download/1dc7c27b64c47fad?user=69116
    
 * 变量格式: export jzkg_data='userid1 @ userid2'  多个账号用 @分割
 *
 * userid   app 页面兑换界面--左上角 有 id

</details>
