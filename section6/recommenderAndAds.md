# 推荐系统/计算广告专题

### 推荐系统
- 协同过滤仅需要一个 **user-item** 矩阵（矩阵元素为打分值），并不需要user和item的属性。可以视作矩阵补全问题。

- 基于内容
    - 缺点： 推荐物较为静态
- 基于社交(社会化推荐)
- 基于当前情景


- 冷启动问题
- 推荐差异化



### 知识图谱(knowledge graph)
参考：[知识图谱技术原理介绍](http://weibo.com/p/23041872d083c70102vye8)

知识图谱：机器大脑中的知识库

知识图谱旨在描述真实世界中存在的各种实体或概念。其中，每个实体或概念用一个全局唯一确定的ID(标识符, identifier)来标识。每个属性-值对（attribute-value pair，又称AVP）用来刻画实体的内在特性，而关系（relation）用来连接两个实体，刻画它们之间的关联。

实体链接

关系抽取

知识推理

知识表示



- 知识表示代表模型：TransE

    对事实（head, relation, tail），将relation看做head到tail的翻译  
    存在的问题：无法解决一对多，多对一和多对多的情形

- 关系路径的表示和建模
- 

- 知识图谱的嵌入（knowledge graph embedding）

    即将实体和关系投影到连续的向量空间中去

wikidata

freebase 已经被谷歌霍霍关闭了。

- [TransG: A Generative Mixture Model for Knowledge Graph Embedding](http://arxiv.org/pdf/1509.05488.pdf)



### 产品化细节

上翻后引导

直接返回答案





### 计算广告

- 转化率 

    CVR = conversations/clicks

- pVCR

- [Ad Click Prediction: a View from the Trenches](http://static.googleusercontent.com/media/research.google.com/en//pubs/archive/41159.pdf) by H. Brendan McMahan, et al., google, 2013

    来自谷歌广告一线战壕的干货。FTRL-Proximal 在线学习算法

