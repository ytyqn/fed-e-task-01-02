# fed-e-task-01-02
1. 引用计数的工作原理：
    - 给每个活动对象分配一个计数，代表被引用的次数，在代码执行中会不断地修改这个计数，当计数为0时，触发垃圾回收，将计数为0的垃圾对象回收

    引用计数的优缺点：
    - 优点
        - 能够即时回收垃圾对象；
        - 减少程序暂停，因为内存空出来了
    - 缺点
        - 有变量循环引用，内存不释放的问题；
        - 一旦活动对象很多，修改计数消耗资源较大
2. 标记整理
    - 遍历活动对象进行标记，再将标记对象和无标记对象进行内存整理，所有标记对象聚合放一边，所有无标记对象聚合放在另一边，之后对无标记对象集合进行清除回收
3. V8新生代回收流程
    - 将新生代内存分为两个等大的空间
    - 使用空间为From，空闲空间为To
    - 每当有新生对象诞生，就会在 From 空间出现
    - 当From存储到一定空间时会触发GC即标记整理
    - 标记整理后将整理的活动对象（From中包含活动和不活动对象，这里只copy活动对象）copy到To
    - 之后将From变成To释放内存（这样就可以实现把不活跃的对象给回收掉），而To变成From，开始下一轮循环

4. 增量标记算法是为了解决标记大型内存的性能问题，面对大型内存是需要使用增量标记。目前又有一个并发标记来解决这个问题，而且该技术可以让 GC 扫描和标记对象时，同时允许 JS 运行

    工作原理：
    - 在增量标记期间，GC 将标记工作分解为更小的模块，可以让 JS 应用逻辑在模块间隙执行一会，从而不至于让应用出现停顿情况

# 代码题1
#### 练习1-代码路径：
#### 练习2-代码路径：
#### 练习3-代码路径：
#### 练习4-代码路径：
# 代码题2
#### 练习1-代码路径：
#### 练习2-代码路径：
#### 练习3-代码路径：
#### 练习4-代码路径：