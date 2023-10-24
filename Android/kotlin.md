# Coroutine
## CoroutineExceptionHandler
### Overview
1. 结构化并发
每个任务有独立的生命周期，子任务继承父任务的生命周期。父任务取消，子任务跟着取消。

2. 异常传递流程
    1. 取消子协程
    2. 取消自己
    3. 将异常传递给父协程
    4. 重复此过程直至根协程关闭

3. 异常传递特性
当子协程发生异常时，会优先将异常传递给父协程处理（根协程或协程初始化时）。所以异常不会被子协程的CoroutineExceptionHandler捕获。SupervisorJob除外

### SupervisorJob
1. 子协程自己处理异常，不会影响兄弟协程和父协程。
2. launch时指定的SupervisorJob不会被传递到新launch的子协程中，因为新launch的子协程默认会使用新的Job替代SupervisorJob，所以想让新launch的子协程不影响其他协程，需要显式增加SupervisorJob。
3. SupervisorJob只能作用于同一级别的子协程。但如果在初始化scope时添加了SupervisorJob，那么该scope对应的所有根协程都默认携带SupervisorJob。
async有问题

### try不住的异常
在try中使用了launch开启新的子协程中发生的异常无法被tryCatch捕获。因为此子协程中的异常发生后传递给了该子协程，然后该子协程直接传递给了父协程，未经过try的作用域。

### CoroutineExceptionHandler失效
1. async如果对应的是根协程则会在调用处（await）暴露异常；如果不是根协程，则会优先将异常传递给父协程，
1. 在async中使用SupervisorJob() + CoroutineExceptionHandler无法将异常在此协程中处理掉。
2. 可以先使用SupervisorJob，不让异常传递；再使用runCatching在await处包裹得到结果。

### SupervisorScope
其内部协程的Job都是SupervisorJob。


# 泛型
## Producer
子赋值给父
上界通配符 ? extends -> get -> 对外提供数据
## Consumer
父赋值给子
下界通配符 ? super -> add -> 消费数据

