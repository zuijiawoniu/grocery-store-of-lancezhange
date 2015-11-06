# 常用算法总览


- 逻辑回归
   损失函数为交叉熵

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
- CNN(卷积神经网络)
    - VGG architecture
    - 
- RNN（recurrent neural networks）
    RNN更加适合 sequential data.
    - LSTM
        [谷歌的邮件智能回复](http://googleresearch.blogspot.co.uk/2015/11/computer-respond-to-this-email.html)
- 递归神经网络(Recursive Neural Nwtwork)

- 深度学习(deep learning)
    - 深度学习的核心在于学习多层次的表示（对应不同程度的抽象）
    - data -> information -> knowledge ->  wisdom
    - distributed representations
    - [videolecture: 深度学习暑期学校](http://videolectures.net/deeplearning2015_bengio_theoretical_motivations/),2015,蒙特利尔
    - 

- Memory Networks

- RAM(Reasoning,Attention, Memory)

- PageBrain
    谷歌用以搜索结果排序的人工智能系统


