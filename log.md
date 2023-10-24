# log
NEWGS-23193 = 3

# 需加字串

如果是从三方打开网页版的报告，不管是不是本人，没有此按钮

# 需做
1. 没有toolbar的用BaseFragment
2. pageAdapter中不是必填项的使用set方法填入
3. lateinte谨慎使用，fragment重建时可能不会走初始化
4. 所有的异常都需用Timber log
5. loadmore刚好为20个时，不仅需要判断list size，还要判断start是否为0

# 问题
1. 如果更改了Density，那么createBitmap也需要增加Density

# viewBinding = null的原因
1. postDelay未取消，在onPause中取消，若在onDestroy中取消可能晚了


模拟滑动：adb shell input swipe 720 1560 720 100 100
返回 ： adb shell input tap 100 100
