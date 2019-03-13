新品葱因为续存及高强度匿名需要而[公开备份后台数据库](https://pincong.rocks/article/98)，因为数据库公开而被爆出[时区泄漏漏洞](https://pincong.rocks/article/575)，值得肯定的是站方已经采取补救措施。
但其实几乎所有的论坛都存在时区泄漏问题，因此这个问题值得所有敏感用户注意，因为绝大多数网站没有像品葱这样注重安全，一旦数据库被入侵或遇到钓鱼网站就会如此情况。

# [原文备份精选整理如下](https://pincong.rocks/article/98)

大家注意，新品蔥雖然對發帖/發文時間雖然作了模糊處理，但僅僅是在前臺只顯示日期，而後臺則是完整的時間記錄（年月日時分秒）。而只需要20次發帖就能泄漏你所在的地理位置，無人能幸免。

下面向大家展示一些熱門用戶的活動時間經驗分布函數，時間從UTC時間0點開始至24時結束，曲線中越平坦的時間段活動越少，越陡峭的時間段活動越多。

同時，本報告也是提醒大家大數據分析的威力（這僅是單一的時間分析），要有敬畏之心，切勿掉以輕心。

建議：
高危用戶如@admin @小二 請選擇固定一天當中的僅僅某一個小時發帖。
你們一個發帖不到30貼，另一個盡量隨機登錄，但仍然能判斷你們在中國大陸時區。
建議這兩個ID今後僅僅用於站務。

![cdf](https://i.imgur.com/kiOjQ5N.gif)

@陈士杰 大家絕對不要再相信這個賬戶，他原先說自己是大陸人在美國，後來又說自己是舊賬戶的朋友（原话是“原来那个陈世杰回国了”），但實際上其活動時間顯示這個ID絕對不是一個自然人的賬戶，根本没有睡眠时间，這個ID的活動時間顯示其是由一個遍布全球的機構控制，具体动机这里不作猜测。

![cdf](https://i.imgur.com/ysvoz6Z.png)

@一只鹿兒 你的作息很有規律，生活質量很高，每天8小時睡眠很健康，中午吃飯午休都很規律。加油！

![cdf](https://i.imgur.com/gJ3w9jc.png)

下面三位熱門用戶來自臺灣或大陸，這裏隱去ID

![cdf](https://i.imgur.com/2zetcDX.gif)

下面三位熱門用戶來自北美和歐洲（恭喜肉翻）僅點名@SALTYATO 你真的在密歇根

![cdf](https://i.imgur.com/5HbaQLW.gif)

最佳安全獎：唯一一位有意識控制自己活動時間的是最新注冊並比較活躍的@anonym 無法根據其活躍時間分辨出他是來自北美還是大陸/臺灣。
![cdf](https://i.imgur.com/HOmSWCV.png)

整改建議： 

+（1）品蔥頁面頂部顯示主要時區的時間，北京/臺北、美東、UTC（英國），方便用戶進行時間管理。
+（2）修改問題/文章的延遲發布機制，將其隨機化到24小時，發布後清除真正的原始發布時間。
+（3）敏感用戶請嚴格限制自己上品蔥的時間，學習@anonym 的時區模糊法，或限制在某一个小时。

### 回复1
发布这个漏洞是为了提醒大家不要掉以轻心，主动安全措施。这里判断大家时区的不是上品葱的时间段，而是不上品葱的时间段（相对其他时段比较平坦，长度6-8小时左右的时段），对没有采取主动措施的自然人用户来说，就等于你的睡眠时间段。
另外除了数据外，文字描述上我刻意加入了一些错误。

陈士杰这个ID不是自然人而是由一个遍布全球不同时区的机构控制，他根本没有睡眠时间，但却刻意假装自然人，该机构的具体动机这里不猜测。

@小二 经验分布函数是概率密度函数的积分，它能从很少量数据提取出细微的统计规律，而这些细节换成概率密度则容易被忽略。

@PincongBot 作息不规律的人也有规律，@小二 在随机化自己的访问时间上是做得最好的，但睡眠时间段内的活动频繁度仍然比非睡眠时间段略低。

@admin 延迟发布的机制不够完善，不要过度依赖，另外它只往后延迟，因此几乎可以推断出每个用户的起床时间。

其他某些回复本帖的ID刚好已经在贴出来的数据中，根据平时发言可以判断你的时区。

建议敏感用户采取@anonym 的办法，在两个主要时区（如北美+东八）的睡眠时段保持绝对沉默。 

### 回复2 bugreport002
那今天就得罪一下，挂几个墙外的和特别不信邪的
@SALTYATO 美东

@Pepperoni 美东

@vvgvv1 欧洲

@由比滨结衣 欧洲 主要非上班时间活动

@薄熙来 欧洲 （随机化做得较好）

@viewer 欧洲 （随机化做得很好）

@adbase 澳洲时段

@利维坦 澳洲时段

@guibuhai 澳洲+亚洲双时区 （双时区覆盖）

@1901zxc 东八区

@钱宝盛 东八区 坐实五毛

其他东八区的就不挂了

部分ID下班时间2小时间隔可推测身处大城市

### 解决方案
__可利用国际会议排时网站寻找公共非睡眠时间段__
[https://www.timeanddate.com/worldclock/meeting.html](https://www.timeanddate.com/worldclock/meeting.html)

三时区 伦敦+纽约+北京 公共非睡眠时段，北京时间20-22时

双时区 北京+纽约 公共非睡眠时段，北京时间早8-10时，晚20-22时