# 数据科学工具

武库中，要有匕首短刀，也要有大刀长矛，要有神鞭，也要有铁锤，总之要丰富，在不同的场景下用称手的武器，才能手到擒来。

随着越来越多的机器学习工具加入开源社区，整个机器学习工具领域呈现出百花齐放的局面。

### Spark

Spark 被认为是 ***smartphone of data***

##### 基础
job stage task

DAGScheduler *作业调度*模块, 基于Stage的高层调度模块，它为每个Spark Job 计算具有依赖关系的多个 Stage 任务阶段（通常根据 Shuffle 来划分 Stage，如 groupByKey, reduceByKey 等涉及到shuffle的变换就会产生新的stage），然后将每个 Stage 划分为具体的一组任务，以 TaskSets 的形式提交给底层的 *任务调度* 模块 TaskScheduler 来具体执行

TaskScheduler 本身是由 SchedulerBackend 来调度和管理的。

执行步骤
0. 根据 SparkConf 进行一系列的初始化
1. SparkContext 创建 DAG Scheduler 和 TaskScheduler
2. TaskScheduler 通过 SchedulerBackend 创建 AppClient
3. AppClient 向 Master 提交 Application
4. Master 根据 AppClient 的提交选择 Worker
5. Worker 根据 Master 的资源分配结果来创建 Executor



[spark 中的编程模型](http://blog.csdn.net/liuwenbo0920/（）article/details/45243775)


##### 性能调优

spark.executor.memory


不用 `readuceByKey`

`spark.driver.maxResultSize`

`spark.akka.frameSize`



###### 高级开发
[Sparknet: training deep networks in spark, by Philipp Moritz, et al., berkeley](http://arxiv.org/pdf/1511.06051v1.pdf)

[gitbook: Spark 开发指南](https://www.gitbook.com/book/taoistwar/spark-developer-guide/details)

### Scikit-Learn

### H2O

### Weka

### Vompal Wabbit

### Hadoop

[Hadoop NameNode 高可用性实现解析](http://www.ibm.com/developerworks/cn/opensource/os-cn-hadoop-name-node/)

- 默认的 block_size 为64M.
- 默认的调度策略： FIFO
- combiner 作为本地化的reduce,指的是先对 map 端的输出先做一次合并，以减少在map 和 reduce 节点之间的数据传输，以提高网络IO性能。但 combiner 可能不会被执行。
- 通常集群的最主要瓶颈就是磁盘IO.

### caffe

### torch

### theano

### [Keras](http://keras.io/)

**`Keras`**在德语中的意思为‘号角’


### [TF(tensorFlow)](http://tensorflow.org/)
谷歌开源的第二代深度学习系统，参看 [Jeff Dean 的介绍](http://vdisk.weibo.com/s/tQWXdywczVZO) 和[官方白皮书(译)](http://www.jianshu.com/p/65dc64e4c81f).

第一代是 DistBelief, 其可扩展性较好，但灵活性不足

然而 TF 一出，对其[性能的评测结果](https://github.com/soumith/convnet-benchmarks/issues/66)却并不理想，被戏称为 *TensorSlow*，一时间舆论大哗。



### [DMTK](http://www.dmtk.io/)
DMTK(distributed machine learning toolkit)，由微软开源，包含DMTK分布式机器学习框架，LightLDA, Distributed (Multisense) Word Embedding等组件。

### [MXNet](https://github.com/dmlc/mxnet/)
DMLC 出品。CXXNet 的进化版，支持 python, R, Go, Julia 等多种语言接口，绝对是深度学习领域最为野心勃勃的项目之一。高质量的[设计文档](http://mxnet.rtfd.org/)和示例，是学习的好材料。

特色/优势
1. 借助 mshadow 模块，CPU 与 GPU 不必在代码层面区分，即只写一份代码（这是咋做到的？）。
2. 符号式编程(symbolic programming)和命令式编程的结合。

    符号式编程将定义运算图的步骤和编译运算的步骤分离。
    我个人理解，符号式编程和命令式编程的区别在于，拿多项式求值作例子，后者是直接往式子里代入数值，然后一步一步计算，而前者先做多项式化简，到最后没法化简了再代入数值求结果。有些多项式看着比较复杂，但经过化简可能最后就剩一两项，因此符号式编程更为节省计算量。此外，符号式编程由于明示了最后的结果(计算的边界)，中间结果一概不管，因此可以重复利用内存，节省空间占用，当然，命令式程序也有垃圾回收机制，但因为是编译器通用的垃圾回收策略，可能并不会像符号式程序里的效率这么高。
3. 利用参数服务器，容易分布式扩展
4. 

### [SystemML](http://systemml.apache.org/)
Apache SystemML，IBM 开源的分布式、命令式机器学习平台，目前仍然处于孵化阶段


