# 深度学习专题


### 顶尖研究机构
- MSR

- Facebook 的人工智能实验室 (FAIR, facebook AI research)

    人员方面，有 Yann LeCun，有VC维和SVM的缔造者Vladimir Vapnik，提出随机梯度下降法的Léon Bottou，做出高性能PHP虚拟机HHVM的Keith Adams, 以及 Rob Fergus, Jason Weston, Marc'Aurelio Ranzato,  Tomas Mikolov, Florent Perronnin, Piotr Dollar, Hervé Jégou, Ronan Collobert, Yaniv Taigman等

- 百度IDL


---

### 深度学习(deep learning)通用理论基础

深度学习的核心在于学习多层次的表示（distributed representations，对应不同程度的抽象），从而实现DIKW金字塔(data -> information -> knowledge ->  wisdom).


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








---

###  CNN(卷积神经网络)专题

CNN 已经有了诸多成熟的架构

- LeNet
- AlexNet
- googleNet

    [Going deeper with convolutions](http://arxiv.org/pdf/1409.4842.pdf)


- VGG-Net

　[very deep convolutional networks for large-scale image recognition](http://arxiv.org/pdf/1409.1556.pdf)


- OverFeat

    [OverFeat: Integrated Recognition, Localization and Detection using Convolutional Networks](http://arxiv.org/pdf/1312.6229.pdf)

- R-CNN

    [R-CNN: Regions with Convolutional Neural Network Features](https://github.com/rbgirshick/rcnn)


- ShCNN

    [Shepard Convolutional Neural Networks by Jimmy SJ. Ren, et al., NIPS 2015](https://papers.nips.cc/paper/5774-shepard-convolutional-neural-networks.pdf)

    SenseTime(商汤科技，一家专注于计算机视觉和深度学习原创技术的中国公司)研究人员出品，[代码在此](https://github.com/jimmy-ren/vcnn_double-bladed/tree/master/applications/Shepard_CNN)。可用在超分辨率重建，图像修补等。


---

### RNN（recurrent neural networks, 循环神经网络）专题

本文是一些关于 RNN 的东西，更多资料参见[Awesome RNN](http://jiwonkim.org/awesome-rnn/)

RNN 是 Recursive Neural Nwtwork(递归神经网络，有时也被简写为 RNN) 的一种，其核心在于对当前的状态保留`记忆`（以隐变量的方式存在）。

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

- [A Critical Review of Recurrent Neural Networks for Sequence Learning](http://arxiv.org/abs/1506.00019v1)

- [Scheduled Sampling for Sequence Prediction with
Recurrent Neural Networks](http://arxiv.org/pdf/1506.03099v3.pdf) by Sami Bengio, et al., at Google.

    定时采样


[recurrent.js](https://github.com/karpathy/recurrentjs) Karpathy 大神用　javascript 写的RNN库


更多请参考　[Awesome RNN](http://jiwonkim.org/awesome-rnn/)



---

### 神经变分推断(neural variational inference)





---
### 深度隐变量模型(deep latent variabl models)

[Neural Variational Inference for Text Processing, by Yishu Miao, et al., Oxford, ICLR 2016, under review](http://arxiv.org/pdf/1511.06038v1.pdf)


---

### RNTN（Recursive Neural Tensor Networks）递归神经张量网络

---

### Memory Networks

[End-to-End Memory Networks by Sainbayar Sukhbaatar, et al., 2015](http://arxiv.org/pdf/1503.08895v4.pdf)



- [Memory-based Bayesian Reasoning with Deeep Learning](http://blog.shakirm.com/wp-content/uploads/2015/11/CSML_BayesDeep.pdf)

    to read

- [Ask Me Anything: Dynamic Memory Networks for Natural Language Processing](http://arxiv.org/pdf/1506.07285v1.pdf)





---

### 深度学习的多种应用

深度学习的主要应用我们分专题讲述，以下是一些未分类的其他应用

- [Predicting online user behaviour using deep learning algorithms by Armando Vieira](http://arxiv.org/abs/1511.06247v1)

    预测在线用户行为

- [Using Neural Networks for Click Prediction of Sponsored Search](http://arxiv.org/abs/1412.6601)

　　点击率预测

- [Convolutional Neural Networks for Pedestrian Detection](https://github.com/DenisTome/DeepPed)

    行人检测

- [Neural Turing Machines](http://arxiv.org/abs/1410.5401)

    代码[在此](https://github.com/shawntan/neural-turing-machines)

- [Reinforcement Learning Neural Turing Machine](http://arxiv.org/abs/1505.00521)


- [Neural-Colorizer](https://github.com/YerevaNN/neural-colorizer)

　　利用卷积自编码为灰度图着色

- [用深度卷积神经网络下围棋](http://jmlr.org/proceedings/papers/v37/clark15.pdf)
这背后用到的原理阐述。

- [Neural Programmer-Interpreters by Scott Reed, et al., ICLR 2016, submitted](http://arxiv.org/abs/1511.06279)

    利用深度学习运行计算机程序，这听起来是如此虚幻。


- [opinion mining with deep recurrent nets](http://www.cs.cornell.edu/~oirsoy/drnt.htm)

    观点挖掘





---

### 对抗样本和对抗网络


所谓对抗 样本是指将实际样本略加扰动而构造出的合成样本，对该样本，分类器非常容易将其类别判错，这意味着光滑性假设(*相似的样本应该以很高的概率被判为同一类别*)某种程度上被推翻了。<!--more-->

[Intriguing properties of neural networks, by Christian Szegedy at Google, et al，2014](http://arxiv.org/pdf/1312.6199.pdf). 这篇论文应该是最早提出对抗样本概念的。论文指出，包括卷积神经网络在内的深度学习模型在对抗样本面前都十分脆弱，从而将矛头直指深度学习，似乎要为深度学习热潮降一降温。

[*Deep Neural Networks are Easily Fooled: High Confidence Predictions for Unrecognizable Images*, by Nguyen A, et al, CVPR 15](http://arxiv.org/pdf/1412.1897.pdf)一文更是发现，面对一些人类完全无法识别的样本（论文中称为 **Fooling Examples**），深度学习模型居然会以高置信度将它们进行分类，例如将噪声识别为狮子。这意味着这些模型很容易被愚弄，例如垃圾邮件发送者可能利用对抗样本来骗过垃圾邮件识别系统，目下依赖人脸验证的人脸支付等新潮科技也将面临巨大风险。当然了，只要谷歌不公开他们的垃圾邮件过滤模型的架构，骗子们似乎也无法针对它大规模制造对抗样本，所以我们不用过分紧张，把模型藏好就可以了。然而，可怕的是，在不同训练子集上用不同的架构学习的不同的模型，居然能够被同一套对抗样本愚弄！这意味着骗子们可以自己训练出一个模型，并在此模型上找到一组对抗样本之后就能通吃其他模型了，想想还真是可怕。

那么，对抗样本只是我们的模型照顾不到的一小部分法外之地吗？论文 [Exploring the Space of Adversarial Images(ICLR 2016, under review)](http://arxiv.org/abs/1510.05328)(代码在[这里](https://github.com/tabacof/adversarial))给出了否定的答案，至少在图像空间中，对抗图片绝非孤立点，而是占据了很大一部分空间！[作者放出的生成对抗图像的代码在此](https://github.com/tabacof/adversarial)。

这些研究的提出，一方面促使人们更深入思考机器和人的视觉的真正差异所在，一方面，加上深度模型本身具有的不可解释性缺陷，也让一些人开始认为深度学习不是*deep learning*, 而是*deep flaw*.对深度学习来说，这多少是不公平的指责，因为 kdnuggets上的一篇文章[(Deep Learning’s Deep Flaws)’s Deep Flaws, by Zachary Chase Lipton](http://www.kdnuggets.com/2015/01/deep-learning-flaws-universal-machine-learning.html)指出，深度学习对于对抗样本的脆弱性并不是深度学习所独有的，事实上，这在很多机器学习模型中都普遍存在（Box 大人不就说吗，*all models are wrong, but some are useful*），而深度学习反而可能是目前为止对对抗训练最有抵抗性的技术。这篇文章吸引了包括 Bengio 大牛、Ian Goodfellow 等在内的许多人的热烈讨论，Ian Goodfellow（八卦一下，Ian Goodfellow 是 Bengio 的高徒，目前任职于谷歌，是对抗网络方面的大牛）更是结合这些评论和自己的工作，写了另外一篇文章： [Deep Learning Adversarial Examples – Clarifying Misconceptions](http://www.kdnuggets.com/2015/07/deep-learning-adversarial-examples-misconceptions.html)，中文翻译在此：[深度学习对抗样本的八个误解与事实](http://m.csdn.net/article_pt.html?arcid=2825248)。


那么，导致深度模型对反抗样本力不从心的真实原因有哪些呢？一般我们知道，可能是模型过拟合导致泛化能力不够，泛化能力不够可能是由于模型均化不足或者正则不足，然而，通过更多模型均化和加入更多噪声训练等方式来应对对抗样本的企图均告失败。另外一个猜测是模型的高度非线性，深度模型动辄千百万的参数个数确实让人有点不太舒服（冯诺依曼不就说吗，给他四个参数，他就能模拟大象，五个参数，大象就能摇尾巴了（还真有人写论文探讨如何模拟大象，参见[Drawing an elephant with four complext parameters](https://publications.mpi-cbg.de/Mayer_2010_4314.pdf)）），但 Ian Goodfellow 在论文 [explaining and harnessing adversarial examples, ICLR 2015](http://arxiv.org/pdf/1412.6572.pdf) 中，通过在一个线性模型中加入对抗干扰，发现只要线性模型的输入拥有足够的维度（事实上大部分情况下，模型输入的维度都比较大，因为维度过小的输入会导致模型的准确率过低，即欠拟合），线性模型也对对抗样本表现出明显的脆弱性，这驳斥了关于对抗样本是因为模型的高度非线性的解释。事实上，该文指出，高维空间中的线性性就足以造成对抗样本，深度模型对对抗样本的无力最主要的还是由于其线性部分的存在（*primary cause of neural networks’ vulnerability to adversarial perturbation is their linear nature*）。

毫无疑问，对抗样本带来了对深度学习的质疑（如果能借此灭一灭深度学习的虚火，也是好的，现在相关领域的论文，*无深度，不论文*，灌水的太多，随便改一改模型的架构，调一调参数就能发表，结果好了也不知道好的原因 --- 吐槽完毕），但其实这也提供了一个修正深度模型的机会，因为我们可以反过来利用对抗样本来提高模型的抗干扰能力，因此有了*对抗训练(adversarial training)* 的概念。通过对抗训练，相当于加上了一种形式的正则，可以提高模型的鲁棒性。

随着对对抗样本的更多更深入研究，人们逐渐发现，对抗样本并不是诅咒，而是祝福，因为可以利用对抗样本生成对抗网络(GANs)。[Generative Adversarial Networks, by Ian Goodfellow, et al, ](http://arxiv.org/abs/1406.2661) 最早提出了 *GANs* 的概念。在 GANs 中，包含一个生成模型G和一个判别模型D，D要判别样本是来自G还是真实数据集，而G的目标是生成能够骗过D的对抗样本，可以将G看做假币生产者，而D就是警察，通过G和D的不断交手，彼此的技能都会逐渐提高，最终使得G生产的假币能够以假乱真。
受此启发，[Deep Generative Image Models using a Laplacian Pyramid of Adversarial Networks， by Emily Denton, et al](http://arxiv.org/abs/1506.05751)通过为拉普拉斯金字塔中的每一个尺度建立一个生成模型，使得最终生成的图片与自然图片达到肉眼无法区分的地步，代码参见[项目eyescream](https://github.com/facebook/eyescream) 。还有人用 GANs [生成猫脸的图片](https://github.com/aleju/cat-generator)，也有人用它[生成人脸](http://torch.ch/blog/2015/11/13/gan.html)，GANs 真是简直要被玩坏了。进一步，[Conditional generative adversarial nets for convolutional face generationby Jon Gauthier](http://www.foldl.me/2015/conditional-gans-face-generation/)提出了条件生成对抗网络。文中给出了一个将人脸老化并加上笑容的例子，简直碉堡。

![老化笑脸](../images/oldface.png)

注：本文收录于我的博客文章 [对抗样本和对抗网络](http://www.lancezhange.com/2015/11/19/adversarial-samples/)，该博文上次更新时间为　2015-11


----

### 注意机制(attension)专题

本文严重参考了 [Survey on Attension-based Models Applied in NLP, 2015.10.07](http://yanran.li/peppypapers/2015/10/07/survey-attention-model-1.html)和 [Survey on Attention-based Models Applied in NLP](http://yanran.li/peppypapers/2015/10/07/survey-attention-model-1.html)一文。

基于 *Attension* 的模型近年来越来越受重视。Attension 大约在2014年的时候被引入计算机视觉领域，后来逐渐扩张到了NLP.

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




---

### 数据集
[Street View House Numbers(SVHN)](http://ufldl.stanford.edu/housenumbers/)








---

### 学习资料

1. [video lecture: 深度学习暑期学校](http://videolectures.net/deeplearning2015_bengio_theoretical_motivations/),2015,蒙特利尔

2. [Awesome Deep Vision](https://github.com/kjw0612/awesome-deep-vision)

3. [A Statistical View of Deep Learning](http://blog.shakirm.com/wp-content/uploads/2015/07/SVDL.pdf)
    用统计学的视角看深度学习，待认真研读。

4. [Deep Learning](http://goodfeli.github.io/dlbook/)

    Ian Goodfellow, Aaron Courville 以及 Yoshua Bengio　三人合著。

5. [Neural Networks and Deep Learning ](http://neuralnetworksanddeeplearning.com/)

    也许是最好的入门教程？




