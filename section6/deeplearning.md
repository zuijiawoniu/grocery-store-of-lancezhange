# 深度学习专题

### 深度学习(deep learning)
深度学习的核心在于学习多层次的表示（distributed representations，对应不同程度的抽象），从而实现 data -> information -> knowledge ->  wisdom.

### 顶尖研究机构
- MSR

- Facebook 的人工智能实验室 (FAIR)

    人员方面，有 Yann LeCun，有VC维和SVM的缔造者Vladimir Vapnik，提出随机梯度下降法的Léon Bottou，做出高性能PHP虚拟机HHVM的Keith Adams, 以及 Rob Fergus, Jason Weston, Marc'Aurelio Ranzato,  Tomas Mikolov, Florent Perronnin, Piotr Dollar, Hervé Jégou, Ronan Collobert, Yaniv Taigman等

- 百度IDL

### 模型

- CNN(卷积神经网络)
    - VGG architecture
    - 
- RNN（recurrent neural networks）

    RNN 的核心在于对当前的状态保留`记忆`（以隐变量的方式存在）。

    给定输入序列 $$(x_1,x_2, ..., x_T)$$, 一个标准的RNN通过如下迭代方程计算输出序列$$(y_1,y_2, ..., y_T)$$:

    $$
    h_t = sigma(W^{hx}x-t + W^{hh}h_{t-1})
    $$

    $$
    y_t = W^{yh}h_t
    $$

    所谓的记忆重现，就体现在了$$h_t$$ 与 $$h_{t-1}$$ 上了。

    此外，注意到，RNN 各层之间共享一套参数（由此极大减少了待学习的参数数量），训练用到的是 BPTT(backpropagation through time)。

    针对传统 RNN 的各种缺陷，有如下几种改进的 RNN 模型。

    1. LSTM(long short term memory networks)

        一般用 BPTT 训练 RNN 模型时会因为梯度坍塌/爆炸而无法捕捉远距离依赖，而 LSTM 专治此不服。[Understanding LSTM Networks](http://colah.github.io/posts/2015-08-Understanding-LSTMs/) 是一篇不错的介绍文章，里面对 LSTM 有很生动的介绍。Andrej Karpathy 所写的 [The Unreasonable Effectiveness of Recurrent Neural Networks](http://karpathy.github.io/2015/05/21/rnn-effectiveness/) 更是值得一读。[RNN Tutorials 系列文章](http://www.wildml.com/2015/09/recurrent-neural-networks-tutorial-part-1-introduction-to-rnns/)也写的很好，建议一读。

        LSTM 目前已在诸多领域获得了成功，俨然已是最流行的 RNN 模型，[谷歌的邮件智能回复系统](http://googleresearch.blogspot.co.uk/2015/11/computer-respond-to-this-email.html)也采用了 LSTM.

    2. BirDirectional RNNs

        核心想法：t时刻的输出不仅依赖于之前的序列，可能也要依赖于之后的序列

    3. GRU(gated recurrent units)

        包含一个重置门，一个进化门。相比 LSTM 少了一个输出门。

        [Empirical Evaluation of Gated Recurrent Neural Networks on Sequence Modeling](http://arxiv.org/pdf/1412.3555v1.pdf), by Bengio 等人




- 递归神经网络(Recursive Neural Nwtwork)



- Memory Networks

- RAM(Reasoning,Attention, Memory)

### 论文
- *[Sequence to Sequence Learning with Neural Networks](http://papers.nips.cc/paper/5346-sequence-to-sequence-learning-with-neural-networks.pdf)*

    Google 出品.传统的DNN需要的输入和输出都是固定维度的，但在机器翻译这种情景中，输入和输出都是序列(sequence, 不定长)，因此提出了一个通用的序列到序列的方法，直接粗暴。具体地，用多层LSTM将序列映射到一个定长向量，然后用另外一个深层LSTM将该向量解码为序列，好比请了两个翻译。其实请翻译的做法之前就已经有人做了，只不过这里作者请的翻译是RNN的一个变种，即LSTM. 而之所以请LSTM做翻译，是因为LSTM比较擅长处理长距离的时序依赖（体现在句子中就是长距离的单词之间的语义依赖），使得在语言翻译问题中能够得到好的效果。  
    trick：输入序列逆序化能够将效果提升很多，作者认为这是他们论文最大的贡献之一。可能的解释是，反序之后，输入序列和输出序列的平均距离虽然没有变，但最小距离减小很多。


### 学习资料

1. [videolecture: 深度学习暑期学校](http://videolectures.net/deeplearning2015_bengio_theoretical_motivations/),2015,蒙特利尔
