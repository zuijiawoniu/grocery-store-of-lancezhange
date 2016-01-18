# 工业实践

### A/B Testing

产品和决策在互联网行业都要以用户反馈为依据，A/B 测试作为一种控制对比实验手段，在用户反馈分析中有非常重要的应用。

A/B 测试要点

结果的显著性
   　

- [揭秘大众点评网大规模并行A/B测试框架 Gemini](http://www.csdn.net/article/2015-03-24/2824303)


- [Overlapping Experiment Infrastructure: More, Better, Faster Experimentation by Diane Tang, et al., google, 2010](http://static.googleusercontent.com/media/research.google.com/en//pubs/archive/36500.pdf)

    重叠实验架构： 更多、更好、更快地实验。
    更多：我们需要能同时进行多个实验的可扩展性。但是我们也需要灵活性：不同的实验需要不同的配置和不同的流量来衡量实验的统计意义上的效果显著性.
    更好：不合理的实验是不应该让它在线上流量进行的。合理的但是很差的实验（比如，有bug的实验或是无意中产生的很差的实验结果）都应该能很快的被捕获并且停止它的进行。标准化的标价指标可以让所有的实验进行公平的比较.
    更快：能够很容易并且很快地建立一个实验。容易到非工程师不需要写代码就可以创建一个实验。评价指标应该很快的被统计出来，以便分析。简单的迭代可以很快速地进行.
    待读，翻译在[这里](http://ju.outofmemory.cn/entry/112729)，以及[解读](http://blog.sina.com.cn/s/blog_6e654d2b0101hpkr.html)

### 族群分析(cohort analysis)

人群行为分析的一种, 主要用于用户粘性分析, 留存分析




