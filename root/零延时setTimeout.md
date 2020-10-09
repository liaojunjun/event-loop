setTimeout(func, 0) 或 setTimeout(func)。在当前脚本执行完后立即调用，最少的延迟是 4ms。

### 事件循环：微任务和宏任务

一个任务到来时，引擎可能正处于繁忙状态，那么这个任务就会被排入队列。 多个任务组成了一个队列，即所谓的“宏任务队列”

![eventLoop](https://zh.javascript.info/article/event-loop/eventLoop.svg)

1. 引擎执行任务时永远不会进行渲染（render）。如果任务执行需要很长一段时间也没关系。仅在任务完成后才会绘制对 DOM 的更改。
2. 如果一项任务执行花费的时间过长，浏览器将无法执行其他任务，无法处理用户事件，因此，在一定时间后浏览器会在整个页面抛出一个如“页面未响应”之类的警报，建议你终止这个任务。这种情况常发生在有大量复杂的计算或导致死循环的程序错误时。

#### 举例 1：拆分 CPU 过载任务

https://zh.javascript.info/event-loop#yong-li-1-chai-fen-cpu-guo-zai-ren-wu

#### 举例 2：进度指示

https://zh.javascript.info/event-loop#yong-li-2-jin-du-zhi-shi

#### 举例 3：在事件之后做一些事情

https://zh.javascript.info/event-loop#yong-li-3-zai-shi-jian-zhi-hou-zuo-yi-xie-shi-qing

#### 微任务和宏任务

![eventLoop-full](https://zh.javascript.info/article/event-loop/eventLoop-full.svg)
