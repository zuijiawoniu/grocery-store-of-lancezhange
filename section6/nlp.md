# 自然语言处理专题

### 顶会
- ACL 计算机语言学协会

    [ACL Anthology](http://aclweb.org/anthology/index.html)
- NIPS
- EMNLP(Conference on Empirical Methods in Natural Language Processing)

    自然语言处理实证方法会议，2015年9月17-22日在葡萄牙里斯本市召开



[Evaluation methods for unsupervised word embeddings]

传统的自然语言处理方法是从语法，句法到语义的完整链条，每个步骤都需要人工设计特征，而深度学习则是‘端到端’的。

语义表示学习


synset 同义词

systactic parsing 句法分析


- 对齐(alignment)

    对齐，分段落、句子、短语、词语等不同级别

    [词语对齐的对数线性模型](http://nlp.ict.ac.cn/~liuyang/papers/acl05_chn.pdf)


### 文本摘要

A Neural Attention Model for Abstractive Sentence Summarization


语言被认为具有树形结构
### 序列模型 VS 树结构

>在以下两种情况下，我们无需使用树结构模型

> 1、我们面对的是简单问题，其较少考虑长距离的语义依赖关系；
>
> 2、即使面对的是复杂问题，只要我们能够获得足够的训练数据；
>
> by 车万翔



### 分词
中文分词法
    - 基于语法规则
    - 基于词典
        - 最大正向/反向匹配
        - 最大概率
    - 基于统计
        - HMM
        - CRF

### Term Weighting

### 词性标注

### 命名实体识别(Named Entity Recognition)

### 情感分析

### 关系抽取



### 自然语言生成(NLG,natural Language Generation)

语义依存分析
在句子结构中分析实词和实词之间的语义关系，这种关系是一种事实上或逻辑上的关系，且只有当词语进入到句子时才会存在。语义依存分析的目的即回答句子的”Who did what to whom when and where”的问题。
![依存分析](http://mmbiz.qpic.cn/mmbiz/58FUuNaBUjrhHeeViaJ7BibPxDSDlRcI4ZqlIxhFKU7m81PcdVM2LsExgCRzbgTtEhsEJVttdWyc3hALp1ctU6kg/640?wx_fmt=png&amp;tp=webp&amp;wxfrom=5&amp;wx_lazy=1">)

### 机器翻译(MT, Machine Translation)


- PBMT(phrase based machine translation)

- 统计机器翻译(SMT, statistical machine translation)

    包括基于单词，基于短语，基于形态分析（词形变化），基于句法（不再将句子视为无结构的单词序列）
    
    奠基之作：*《A statistical approach to machine translation》*(简称Brown90)


First Order Probablistic Logic
一阶概率逻辑

[A survey of First-Order Probablistic Models](http://cogcomp.cs.illinois.edu/papers/BrazAmRo08.pdf)
[paper: Statistical Phrase-based Translation ](http://dl.acm.org/citation.cfm?id=1073462)

paradigmatic relation

词形变化关系，例如，

> 老虎是一种凶猛的动物，狮子是一种凶猛的动物

则(老虎，狮子)就是词形变化关系，体现在相似的上下文中

syntagmatic relation
组合关系，比如，在前面的例子中，(老虎，凶猛)就是组合关系，它体现在

[Learning Word Representations by Jointly Modeling Syntagmatic and Paradigmatic Relations ]()

RNTN（Recursive Neural Tensor Networks）
递归神经张量网络


feature map

[ Simple Learning and Compositional Application of Perceptually Grounded Word Meanings for Incremental Reference Resolution ]()
- LDA

多模态 - 将文本与图像/音频/视频等结合







- [Sentence to Sequence -- Video to Text](http://arxiv.org/abs/1505.00487v3)

    2015.10. 基于 (video, sentence) pair 训练出 LSTM 模型，称为 S2VT，video 包括像素值和相邻帧的光流。

### 词嵌入(word embeding)
- *[How to Generate a good Word Embeding?](http://arxiv.org/abs/1507.05523)*

    作者本人还写了一篇[博客](http://licstar.net/archives/620)作为论文导读



Deep Learning 成功入侵了语音和视觉领域后，也终于在自然语言处理方面展现了自己的存在。


[Deep Learning in NLP(-): 词向量和语言模型](http://licstar.net/archives/328)

基于 *Attension* 的模型近年来也越来越受重视。Attension 大约在2014年的时候被引入计算机视觉领域，后来逐渐扩张到了NLP.(参见 [Survey on Attension-based Models Applied in NLP, 2015.10.07](http://yanran.li/peppypapers/2015/10/07/survey-attention-model-1.html)）

[Not All Contexts Are Created Equal: Better Word Representations with Variable Attention](http://www.cs.cmu.edu/~lingwang/papers/emnlp2015-2.pdf)

##### 文本生成
[Generating Text with RNN](http://www.cs.utoronto.ca/~ilya/pubs/2011/LANG-RNN.pdf)



### 更多语料
- [WordNet](http://wordnet.princeton.edu/)

    普林斯顿大学的科研人员设计的一个基于认知语言学的英语字典，它将单词按照意义组合成不同的同义词集合，并记录了这些集合之间的层次关系。

- [ConceptNet](http://conceptnet5.media.mit.edu/)

    语义网络，出自MIT

- [FrameNet](https://framenet.icsi.berkeley.edu/fndrupal/home)

    伯克利出品。按照情景(frame)组织，每种情景由其触发词汇。缺点：frame那么多，我们永远也弄不全的！


### 常用工具

- [NLTK]()
- [spaCy](http://spacy.io/)
    号称具有工业强度，用 Cython 编写，比NLTK快400倍

    仅支持英语，且不能在 windows 下使用（这倒没啥大不了的）
- Stanford Core NLP

    还有[python接口](https://github.com/dasmith/stanford-corenlp-python)

#### 学习资料

- [coursera课程： 自然语言处理](https://class.coursera.org/nlp/lecture)

    老师为斯坦福大学的 Dan Jurafsky 和 Christopher Manning
- [Natural Language Understanding: FUndations and State-of-the-Art](http://icml.cc/2015/tutorials/icml2015-nlu-tutorial.pdf)
    须深读之


    ICML 教程之一，待看
- [Speech and Language Processing --- An Introduction to Natural Language Processing, Computational Linguistics, and Speech Recognition](https://www.cs.colorado.edu/~martin/slp.html)

- [Publications of deep Learning in NLP](https://github.com/niangaotuantuan/Publications-of-Deep-Learning-in-NLP/blob/master/neural_lm.md)
