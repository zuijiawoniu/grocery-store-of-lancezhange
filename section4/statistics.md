# 统计基础



统计三大分析：回归分析、方差分析、多元分析

- 共轭分布

    [几何视角看共轭先验](http://www.umiacs.umd.edu/~arvinda/mysite/papers/conjugate.pdf)：选取共轭先验并不仅仅是出于数学上的方便，还有更深层的原因。（很数学化的一篇论文，没耐心读完啊－－－）


- EM 算法


- GAM(广义可加模型)

[GAM: The Predictive Modeling Silver Bullet](http://multithreaded.stitchfix.com/blog/2015/07/30/gam/?utm_campaign=Data%2BElixir&utm_medium=email&utm_source=Data_Elixir_47)



### 概率图模型(PGM, Probablistic Graphical Model)

贝叶斯网络（byaesian networks）、信念网络（belief networks）都是概率图模型的马甲。

贝叶斯统计说白了其实只做了一件事：区分哪些是我们的先验，哪些是证据，区分之后再做联系交互，于是新的证据可能融入并修改之前的先验，新的先验导致新的证据被接受，如此循环。

概率图模型就是将概率依赖关系图示化，并且找到了概率关系与图关系的一种映射，使得我们之前只能借助概率表达和推断的东西也可以直接用图的关系来表达和推断，而图相对来说是更为直观的。这里重要的其实是这种映射关系的存在性。

我们知道，在概率关系中，独立（和条件独立）是非常重要的，正是独立性的存在，可以让我们对问题分而治之，做到简化。概率图模型试图刻画的，也正是变量之间的依赖关系，尤以独立和条件独立为重中之重。



[Probablistic Graphical Models, by Eric Xing](http://www.cs.cmu.edu/~epxing/Class/10708-14/lecture.html)



---

### Dirichlet Process　狄利克雷过程专题



- [Dirichlet Process](http://www.gatsby.ucl.ac.uk/~ywteh/research/npbayes/dp.pdf)

- [A Very Gentle Note on the Destruction of Dirichlet Process ](http://users.cecs.anu.edu.au/~xzhang/pubDoc/notes/dirichlet_process.pdf)

狄利克雷过程混合模型(Dirichlet process  mixture models)

求解狄利克雷混合模型的变分推断方法
参考[Variational Inference for Dirichlet Process
Mixtures](http://www.cs.columbia.edu/~blei/papers/BleiJordan2004.pdf)
