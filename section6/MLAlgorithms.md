# 常用算法总览


- 逻辑回归
   损失函数为交叉熵
- 最近邻
- 近似最近邻(ANN, approximate nearest neighbour)

    - LSH(locality-sensitive hashing)

        基本思想：将原始数据空间中的两个相邻数据点通过相同的映射或投影变换（projection）后，这两个数据点在新的数据空间中仍然相邻的概率很大，而不相邻的数据点被映射到同一个桶的概率很小  
        参考博文：[局部敏感哈希介绍](http://blog.csdn.net/icvpr/article/details/12342159)
- 奇异值分解

    [The Singular Value Decomposition, Applications and Beyond](http://arxiv.org/pdf/1510.08532.pdf)
- 决策树
- CART
- 感知机
- 支持向量机
- Boost
    - AdaBoost
    - GradientBoost

- 朴素贝叶斯
- 极大后验概率(MAP)
- 贝叶斯估计
     - 和 MAP 的最大区别：MAP 假设参数是固定值，而贝叶斯估计假设未知参数也是随机变量。
- 隐马尔科夫
    模型 model = (初始状态, 转移矩阵, 观测概率)

    - 学习问题：已知观测，估计模型，采用 EM 算法
    - 概率计算：在已知模型下得到特定观测的概率，采用前向/后向算法
    - 解码问题：已知模型和观测序列，求最大可能的状态序列，采用维特比算法
- 概率潜在语义分析(pLSA)
- LDA



- sequence-to-sequence learning
- 

- 概率图模型
- 条件随机场



