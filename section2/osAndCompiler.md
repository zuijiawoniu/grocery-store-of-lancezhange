# 操作系统和编译原理

编译步骤
1. 词法分析  有限状态自动机
2. 语法分析  栈的下推自动机，产生 Parse Tree.
3. 代码生成  
4. 

## 编译器的分支预测
例如如下**循环**中的if条件语句
   if(data[i] >= SOME_VALUE){
       //do_something
   }
如果data本身是排好序的，其用时会显著少于data无序的情形，这就是因为编译器会做分支预测，当data有序时，不会频繁跳转分支。

## 非规格化浮点数(Denormal Number)
非规格化浮点数的处理比较耗时

## 页面调度算法

包括 LRU, LFU, FIFO 等，注意区别LRU和LFU，前者是从频率上，后者是从时间上。


### 资料

[gitbook: linux insides](https://www.gitbook.com/book/0xax/linux-insides/details)
[gitbook: 理解 linux 进程](http://www.linuxprocess.com/)
