# 数据挖掘工具

### Spark

### Scikit-Learn

### H2O

### Weka

### Vompal Wabbit

### Hadoop

- 默认的 block_size 为64M.
- 默认的调度策略： FIFO
- combiner 作为本地化的reduce,指的是先对 map 端的输出先做一次合并，以减少在map 和 reduce 节点之间的数据传输，以提高网络IO性能。但 combiner 可能不会被执行。
- 通常集群的最主要瓶颈就是磁盘IO.

