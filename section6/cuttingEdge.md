# 前沿

- [On Learning to Think: Algorithmic Information Theory for Novel Combinations of Reinforcement Learning Controllers and Recurrent Neural World Models by Juergen Schmidhuber, 2015](http://arxiv.org/abs/1511.09249)

    learning to think.


- [Human-level concept learning through probabilistic program induction](http://www.sciencemag.org/content/350/6266/1332.full.pdf)

    发表在《科学》上的文章，通过概率推理来学习概念，在这到处都是深度学习的万花丛中，真是一抹别样红啊。[matlab 代码在此](https://github.com/brendenlake/BPL)

    > People learning new concepts can often generalize successfully from just a single example, yet machine learning algorithms typically require tens or hundreds of examples to perform with similar accuracy. People can also use learned concepts in richer ways than conventional algorithms—for action, imagination, and explanation.

    作者指出了两点人类学习和机器学习新概念的区别：人类学习新的概念是小样本学习(one-shot learning)，而现在的机器学习是大样本的；人类对学习到的概念能够更为灵活和广泛地使用。

    文中提出的新框架：BPL(Bayesian Program Learning, 贝叶斯程式学习)，宣称结合了三个关键想法：组合、因果、学习如何学习。核心在于，用概率程式表示概念，而概率程式由低级概念的程式结合空间关系等组合出来。生成模型的生成模型。


- [Illustration2Vec: A Semantic Vector Representation of Illustrations](http://illustration2vec.net/papers/illustration2vec-main.pdf)

    漫画的语义向量表示。日本东北大学（Tohoku University，简称东北大）和东京大学的研究人员联合出品。

    难点：漫画相比于普通的图片，其形态更加丰富；缺少相关数据集

    还提出了一种语义形变(semantic morphing)算法用以在大量漫画数据中中搜寻相关漫画。

