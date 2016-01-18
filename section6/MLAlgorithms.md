# 常用算法总览

>One good thing about doing machine learning at present is that people actually use it!



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

- 随机森林

    [Awesome Random Forest](http://jiwonkim.org/awesome-random-forest/)

- 感知机
- 支持向量机

- 朴素贝叶斯
- 极大后验概率(MAP)
- 贝叶斯估计
     - 和 MAP 的最大区别：MAP 假设参数是固定值，而贝叶斯估计假设未知参数也是随机变量。


- 隐马尔科夫
    模型 model = (初始状态, 转移矩阵, 观测概率)

    - 学习问题：已知观测，估计模型，采用 EM 算法
    - 概率计算：在已知模型下得到特定观测的概率，采用前向/后向算法
    - 解码问题：已知模型和观测序列，求最大可能的状态序列，采用维特比算法



- 概率图模型
- 条件随机场



---

### 集成方法(Ensembling)专题

集成方法现在真是火的不要不要的。
参考　[Kaggle Ensembling Guide](http://mlwave.com/kaggle-ensembling-guide/) 一文

- AdaBoost
- GradientBoost




---

### 变分推断(variational Inference)

- [Variational Inference for Machine Learning](http://shakirm.com/papers/VITutorial.pdf)

    出自 Shakir Mohamed from Google DeepMind.


---

### Semi-supervised Learning 半监督学习

针对只有极少部分数据有标记而大量数据无标记的情形
参考 [半监督学习](http://www.cnblogs.com/liqizhou/archive/2012/05/11/2496155.html)

常用假设： 聚类假设、流形假设。在聚类假设下，大量未标记示例的作用就是帮助探明示例空间中数据分布的稠密和稀疏区域, 从而指导学习算法对利用有标记示例学习到的决策边界进行调整, 使其尽量通过数据分布的稀疏区域。流形假设是指处于一个很小的局部邻域内的示例具有相似的性质,因此, 其标记也应该相似。这一假设反映了决策函数的局部平滑性。和聚类假设着眼 *整体特性* 不同, 流形假设主要考虑模型的 *局部特性*。在该假设下,大量未标记示例的作用就是让数据空间变得更加稠密, 从而有助于更加准确地刻画局部区域的特性,使得决策函数能够更好地进行数据拟合。


- transductive learning 直推学习

和半监督学习的不同：直推学习将未标记的数据视作测试样本，学习的目的是在这些测试样本上取得最佳泛化能力，也就是说，学习器的目标就是将有标记的样本上获得的知识迁移到无标记的样本（如何做到？）； 而半监督学习并不知道要预测的示例是什么。简单理解为：直推学习是一种‘短视’的学习，而半监督更具长远眼光。




active learning 主动学习

学习器与外部环境有交互，即进行场外援助：对一些样本，学习器向外界求助。



---

### 强化学习(reinforcement learning)

又称为增强学习。策略梯度(policy gradient)是强化学习中重要的方法

- [Policy Gradient Methods](http://www.scholarpedia.org/article/Policy_gradient_methods)




---

### 排序学习(Learning to Rank)

[Learning to Rank using Gradient Descent](http://icml.cc/2015/wp-content/uploads/2015/06/icml_ranking.pdf)






---

### 机器学习不是万能的

机器学习并不是万能的。

- [Machine Learning: The High-Interest Credit Card of Technical Debt](http://static.googleusercontent.com/media/research.google.com/en//pubs/archive/43146.pdf) by D. Sculley, et al.


- [Hidden Technical Debt in Machine Learning Systems](https://papers.nips.cc/paper/5656-hidden-technical-debt-in-machine-learning-systems.pdf) by D. Sculley, et al., Google

    机器学习系统中隐藏的技术债。* Not all debt is bad, but all debt needs to be serviced*．　这些技术债包括：复杂的模型可能会悄然改变抽象边界，CACE(change anything changes everything)，数据依赖等



---

### 资料
[机器学习](http://wenku.baidu.com/course/view/49e8b8f67c1cfad6195fa705?fr=search) by 余凯、张潼

