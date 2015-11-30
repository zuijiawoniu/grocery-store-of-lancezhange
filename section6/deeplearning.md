# 深度学习专题


### 顶尖研究机构
- MSR

- Facebook 的人工智能实验室 (FAIR, facebook AI research)

    人员方面，有 Yann LeCun，有VC维和SVM的缔造者Vladimir Vapnik，提出随机梯度下降法的Léon Bottou，做出高性能PHP虚拟机HHVM的Keith Adams, 以及 Rob Fergus, Jason Weston, Marc'Aurelio Ranzato,  Tomas Mikolov, Florent Perronnin, Piotr Dollar, Hervé Jégou, Ronan Collobert, Yaniv Taigman等

- 百度IDL


### 深度学习(deep learning)通用理论基础

深度学习的核心在于学习多层次的表示（distributed representations，对应不同程度的抽象），从而实现 data -> information -> knowledge ->  wisdom.


- [Representation Learning: A Review and New Perspectives by Yoshua Bengio, et al., 2012](http://arxiv.org/abs/1206.5538)

    表示学习

greedy layerwise pre-training 将深度网络分解成几个浅层网络，每层用无监督方法训练

gradient-based learning

Restricted-Boltzman Machine

Stacks of RBMs forms a deep belief network (DBN)
即，受限玻尔兹曼机堆叠成为深度信念网络
Stacks of slightly modified RBMs can form a deep Boltzmann machine (DBM).

Autoencoders

Enery-based Models  分为有潜变量和无潜变量的情形；极大似然方法学习参数






深度学习的主要应用我们分专题讲述，以下是一些其他应用

- [Predicting online user behaviour using deep learning algorithms by Armando Vieira](http://arxiv.org/abs/1511.06247v1)

- [Using Neural Networks for Click Prediction of Sponsored Search](http://arxiv.org/abs/1412.6601)


- [Neural Turing Machines](http://arxiv.org/abs/1410.5401)

    代码[在此](https://github.com/shawntan/neural-turing-machines)

- [Reinforcement Learning Neural Turing Machine](http://arxiv.org/abs/1505.00521)



---

###  CNN(卷积神经网络)

CNN 已经有了诸多成熟的架构。比如， googleNet, LeNet, 
- VGG architecture


[用深度卷积神经网络下围棋](http://jmlr.org/proceedings/papers/v37/clark15.pdf)
这背后用到的原理阐述。





---

#### RNN（recurrent neural networks, 循环神经网络）

本文是一些关于 RNN 的东西。
RNN 是 Recursive Neural Nwtwork(递归神经网络，有时也被简写为 RNN) 的一种

[Awesome RNN](http://jiwonkim.org/awesome-rnn/)

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

- [An Empirical Exploration of Recurrent Network Architectures by Rafal Jozefowicz, et al., Google](http://jmlr.org/proceedings/papers/v37/jozefowicz15.pdf)

    探讨 RNN 的内在机理。非常重要的一篇，待认真研读。

- [Scheduled Sampling for Sequence Prediction with
Recurrent Neural Networks](http://arxiv.org/pdf/1506.03099v3.pdf) by Sami Bengio, et al., at Google.

    定时采样



Multimodal RNN

一些应用（不包括机器翻译等独立专题部分）

- [Neural Programmer-Interpreters by Scott Reed, et al., ICLR 2016, submitted](http://arxiv.org/abs/1511.06279)

    利用深度学习运行计算机程序，这听起来是如此虚幻。

- [A Neural Algorithm for Artistic Style by Leon A. Gatys, et al., 2015](http://arxiv.org/abs/1508.06576)

    


其他如 Memory Networks

[End-to-End Memory Networks](http://arxiv.org/pdf/1503.08895v4.pdf)

RAM(Reasoning,Attention, Memory)

- [Memory-based Baysian Reasoning with Deeep Learning](http://blog.shakirm.com/wp-content/uploads/2015/11/CSML_BayesDeep.pdf)

    to read






### 机器翻译(MT, Machine Translation)
本文介绍机器翻译。

NMT(Neural Machine Translation)

- *[Sequence to Sequence Learning with Neural Networks](http://papers.nips.cc/paper/5346-sequence-to-sequence-learning-with-neural-networks.pdf)*

    Google 出品.传统的DNN需要的输入和输出都是固定维度的，但在机器翻译这种情景中，输入和输出都是序列(sequence, 不定长)，因此提出了一个通用的序列到序列的方法，直接粗暴。具体地，用多层LSTM将序列映射到一个定长向量，然后用另外一个深层LSTM将该向量解码为序列，好比请了两个翻译。其实请翻译的做法之前就已经有人做了，只不过这里作者请的翻译是RNN的一个变种，即LSTM. 而之所以请LSTM做翻译，是因为LSTM比较擅长处理长距离的时序依赖（体现在句子中就是长距离的单词之间的语义依赖），使得在语言翻译问题中能够得到好的效果。  
    trick：输入序列逆序化能够将效果提升很多，作者认为这是他们论文最大的贡献之一。可能的解释是，反序之后，输入序列和输出序列的平均距离虽然没有变，但最小距离减小很多。


- PBMT(phrase based machine translation)

- 统计机器翻译(SMT, statistical machine translation)

    包括基于单词，基于短语，基于形态分析（词形变化），基于句法（不再将句子视为无结构的单词序列）

    奠基之作：*《A statistical approach to machine translation》*(简称Brown90)









---

### 对抗样本和对抗网络
参见我的博客文章 [对抗样本和对抗网络](http://www.lancezhange.com/2015/11/19/adversarial-samples/)




----

### 注意机制(attension)

基于 *Attension* 的模型近年来也越来越受重视。Attension 大约在2014年的时候被引入计算机视觉领域，后来逐渐扩张到了NLP.

注意机制的核心问题在于：如何确定在哪里倾注注意力。就好比老师在期末考试复习的时候告诉大家要抓重点，但真正的问题在于重点在哪里。

软对齐模型(soft alignment models) 和硬对齐模型(hard alignment models)

硬注意机制每次只注意一个地方，而软注意机制只在一个地方倾注相对更多的注意而已。因此，前者需要随即抽样，需要的计算量相对少一些，而后者是确定性的，虽然计算量大一点，但可以用后向传播训练并因此容易嵌入其他网络。

图片描述和MT的区别：后者存在一个粒度(granularity)问题。比如，应该说图片中有一只猫，还是说有一只看起来很慵懒的眯着眼睛的大花猫？



和 saliency 的区别和联系: bottom up saliency, top down attention

- [Recurrent Models for Visual Attention](http://arxiv.org/abs/1406.6247)

- [Neural Machine Translation by Jointly Learning to Align and Translate by Dzmitry Bahdanau, et al., ICLR 2015.](http://arxiv.org/abs/1409.0473)

    这篇文章应该是最早将注意机制从视觉引入自然语言处理的，Yoshua Bengio 也是作者之一。我们知道，基于深度学习的机器语言翻译采用的是 *编码-解码* 的方式，通过对解码端引入视觉机制，减轻了编码端的压力。

- [Encoding Source Language with Convolutional Neural Network for Machine Translation by Fandong Meng, et al., 中科院](http://arxiv.org/abs/1503.01838)

    也是机器翻译领域的。

- [Effective Approaches to Attention-based Neural Machine Translation by Minh-Thang Luong, et al., EMNLP 2015, camera-ready version](http://arxiv.org/abs/1508.04025)

    集成了全局和局部两种注意机制后得到的结果更好。

- [A Neural Attention Model for Abstractive Sentence Summarization by Alexander M.Rush, et al., 2015](http://arxiv.org/abs/1509.00685)

    首次将注意机制引入了句子摘要问题。

- [DRAW: A Recurrent Neural Network for Image Generation by Karol Gregor, et al., Google, 2015](http://arxiv.org/abs/1502.04623)

    提出了一种被称作 *DRAW*(deep recurrent attentive writer) 的用以生成图片的网络架构。主要的一个观察：人在作画的时候也不是一笔挥就一蹴而成，而是经过不断的调整、修改细节才最终成型。因此，DRAW 每次会注意到某个部分，将之修改. 问题在于，如何确定这个注意部分呢？
    和传统的注意机制的不同之处：传统的注意机制中，注意是在解码阶段被引入的，并且不会去影响到编码阶段，而 DRAW 

- [Teaching Machines to Read and Comprehend by Karl Moritz Hermann, et al.,Google, NIPS 2015, to appear](http://arxiv.org/abs/1506.03340)

    教会机器阅读理解。构建了一个 *（（文档，提问），答案）* 数据集。两个模型，*attentive reader* 和 *impatient reader*. 后者需要一遍又一遍地重读文档，

- [Learning Wake-Sleep Recurrent Attention Models by Jimmy Ba, 2015](http://arxiv.org/abs/1509.06812)

    Ruslan Salakhutdinov 也是作者之一。采用了硬注意机制(hard attention mechanism)，

- [Not All Contexts Are Created Equal: Better Word Representations with Variable Attention by Wang Lin, et al.](http://www.cs.cmu.edu/~lingwang/papers/emnlp2015-2.pdf)

    不得不说，文章名称非常有吸引力，

- [Show, Attend and Tell: Neural Image Caption Generation with Visual Attention by Kelvin Xu, et al., 2015](http://arxiv.org/abs/1502.03044)


- [Predicting the Next Location: A Recurrent Model with Spatial and Temporal
Contexts by Qiang LIu, et al., 中科院](http://www.shuwu.name/sw/Predicting%20the%20Next%20Location%20A%20Recurrent%20Model%20with%20Spatial%20and%20Temporal%20Contexts.pdf)

    时空上下文。

- [Policy Gradient Methods](http://www.scholarpedia.org/article/Policy_gradient_methods)

    策略梯度，

数据集
[Street View House Numbers(SVHN)](http://ufldl.stanford.edu/housenumbers/)

本文严重参考了 [Survey on Attension-based Models Applied in NLP, 2015.10.07](http://yanran.li/peppypapers/2015/10/07/survey-attention-model-1.html)和 [Survey on Attention-based Models Applied in NLP](http://yanran.li/peppypapers/2015/10/07/survey-attention-model-1.html)一文。



---

### 神经变分推断(neural variational inference)





---
### 深度隐变量模型(deep latent variabl models)

[Neural Variational Inference for Text Processing, by Yishu Miao, et al., Oxford, ICLR 2016, under review](http://arxiv.org/pdf/1511.06038v1.pdf)






### 学习资料

1. [video lecture: 深度学习暑期学校](http://videolectures.net/deeplearning2015_bengio_theoretical_motivations/),2015,蒙特利尔

2. [Awesome Deep Vision](https://github.com/kjw0612/awesome-deep-vision)

3. [A Statistical View of Deep Learning](http://blog.shakirm.com/wp-content/uploads/2015/07/SVDL.pdf)
    用统计学的视角看深度学习，待认真研读。







