# log
report = 2
web = 3.5
5.5 = 2.5

# 需做
1. ppt中的gs和wechat做分页
2. 列举出具体存在哪些难点
3. UGC和小程序的action bar color为什么要做
4. 小程序头像编辑那里可以注重讲下我们如何做头像和昵称的合规检查的
5. 最后加小程序的开发，克服的苦难
6. 


# 问题
1. 如果更改了Density，那么createBitmap也需要增加Density
2. 视频无法播放
3. preview_card_bg图资有问题，下方有空白间距


# 反思
NEWGS-21950(动态中的文本被识别成网页链接)
原因：
    1. url本身前后端应留空格。
    2. 鸿蒙系统自身会将url识别错误。