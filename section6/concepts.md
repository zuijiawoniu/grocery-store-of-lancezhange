 # 一些概念

#### 经验风险最小化 VS 结构风险最小化

泛化误差上界

#### 生成模型 VS 判别模型


#### 监督学习 VS 无监督学习 VS 半监督学习

#### multi-task learning VS multiclass learning


- VC 维: 精确定义分类器的复杂度
    - 直观定义：单个分类器可最多分类的点个数（不要求对在同一直线上的点分类）
    - N维空间中的线性分类器的VC维为 N+1

#### 偏差和方差(bias VS variance)
均方误差




#### 常用损失函数

- 0-1损失
- 平方损失
- 绝对损失
- 对数损失
- 合页损失

交叉熵

#### 评价函数
- accuracy
- 精度
- 召回
- F值
- AUC
    - AUC 的计算技巧：利用其与 wilcoxon-mann-witney test 的等价性，求出正样本的 score > 负样本的 score 的pair数，但还是复杂。进一步的改进方法：首先对 score 从大到小排序。

#### 对抗样本

*对抗样本*是将实际样本略加扰动而构造出的合成样本，对该样本，分类器非常容易将其类别判错。垃圾邮件发送者可能利用对抗样本来骗过垃圾邮件识别系统。对抗样本对深度模型的影响要比对浅层模型的影响更大，因此一些人认为深度学习不是**deep learning**, 而是**deep flaw**，参见[深度学习对抗样本的八个误解与事实](http://m.csdn.net/article_pt.html?arcid=2825248)

论文 [Exploring the Space of Adversarial Images(ICLR 2016, under review)](http://arxiv.org/abs/1510.05328)
(代码在[这里](https://github.com/tabacof/adversarial)) 显示，对抗图片在像素空间中绝非孤立点，而是占据了很大一部分空间！

由此，有了*对抗训练(adversarial training)* 的概念。通过对抗训练，可以提高模型的鲁棒性，相当于加上了一种形式的正则。
