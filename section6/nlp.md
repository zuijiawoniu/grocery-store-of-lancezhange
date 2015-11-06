# 自然语言处理专题

### 顶会
- ACL 计算机语言学协会
- NIPS
- EMNLP(Conference on Empirical Methods in Natural Language Processing)

    自然语言处理实证方法会议

    2015年9月17-22日在葡萄牙里斯本市召开

    [Evaluation methods for unsupervised word embeddings]

传统的自然语言处理方法是从语法，句法到语义的完整链条，每个步骤都需要人工设计特征，而深度学习则是‘端到端’的。

语义表示学习


synset 同义词

systactic parsing 句法分析

基于 Attension 的网络模型

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

### 词性标注

### 命名实体识别(Named Entity Recognition)

### 情感分析

### 关系抽取

### 自然语言生成(NLG,natural Language Generation)

语义依存分析
在句子结构中分析实词和实词之间的语义关系，这种关系是一种事实上或逻辑上的关系，且只有当词语进入到句子时才会存在。语义依存分析的目的即回答句子的”Who did what to whom when and where”的问题。
![依存分析](http://mmbiz.qpic.cn/mmbiz/58FUuNaBUjrhHeeViaJ7BibPxDSDlRcI4ZqlIxhFKU7m81PcdVM2LsExgCRzbgTtEhsEJVttdWyc3hALp1ctU6kg/640?wx_fmt=png&amp;tp=webp&amp;wxfrom=5&amp;wx_lazy=1">)

### 机器翻译(Machine Translation)

PBMT(phrase based machine translation)

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




### 常用工具

- [NLTK]()
- [spaCy](http://spacy.io/)
    号称具有工业强度，用 Cython 编写，比NLTK快400倍

    仅支持英语，且不能在 windows 下使用（这倒没啥大不了的）
- Stanford Core NLP
    还有[python接口](https://github.com/dasmith/stanford-corenlp-python)

#### 资料

- [coursera课程： 自然语言处理](https://class.coursera.org/nlp/lecture)
    老师为斯坦福大学的 Dan Jurafsky 和 Christopher Manning
- [Natural Language Understanding: FUndations and State-of-the-Art](http://icml.cc/2015/tutorials/icml2015-nlu-tutorial.pdf)
    ICML 教程之一，待看
- [SPEECH and LANGUAGE PROCESSING --- An Introduction to Natural Language Processing, Computational Linguistics, and Speech Recognition](https://www.cs.colorado.edu/~martin/slp.html)

- [Publications of deep Learning in NLP.md](https://github.com/niangaotuantuan/Publications-of-Deep-Learning-in-NLP/blob/master/neural_lm.md)
