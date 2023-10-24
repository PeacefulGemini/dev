# 内存泄漏
1. 长生命周期的对象持有短生命周期的对象，导致短生命周期的对象在生命周期结束后没有被及时回收，导致内存无法复用，最终泄漏。
2. 合理地释放对短生命周期对象的引用。

# 常见的GC ROOT
1. 静态引用
2. 活动的线程

# 匿名内部类
1. 匿名内部类默认持有外部类的引用，会导致外部类无法被回收。
2. 静态内部类不持有外部类的引用，但无法访问外部类的对象。

# Handler泄漏的本质原因
Thread间接持有Handler，Handler持有外部类，最终Thread间接持有外部类，导致泄漏。

# Java匿名内部类是否会泄漏
当外部类销毁时，如果匿名内部类被gc root持有，就会发生内存泄漏

# Java的lambda是否会泄漏
1. lambda没有隐式持有外部类引用。
2. 若lambda内显式持有外部类引用，那么此时和Java匿名内部类一样。

# kotlin的匿名内部类是否会泄漏
和Java的lambda一致

# kotlin的lambda是否泄漏
和Java的lambda一致

# kotlin的高阶函数是否会泄漏
和Java的lambda一致

## 高德地图是否会内存泄漏
1. 9.2.1 修复了mapview泄漏，但必须关闭allowNativeHeapPointerTagging，可随意使用，但销毁时必须onDestroy()
2. 9.2.0 存在内存泄漏，无需关闭allowNativeHeapPointerTagging，但使用方式必须为：实例化传入applicationContext，再addview到layout中，onDestroy的同时将其从layout中remove。


## 参考Link
https://juejin.cn/post/7202583557750636601
https://mp.weixin.qq.com/s/KFoZUPfNO7eF9Givq2AWTw