# 传统计算机视觉专题

### 总论
计算机视觉和自然语言处理这两个领域的发展和命运是很相似的：它们在发展过程中都积累了诸多传统方法，但随着深度学习的崛起，传统方法逐渐失去往日的光辉而显得没落，大地上留下的似乎只剩下深度学习那模糊但强壮的身影。

由于本书单有一章讲深度学习，所以在计算机视觉专题中，我们只讲那些传统的方法，而把深度学习相关的视觉方法放到深度学习那一章去，自然语言处理那里同样如此。

传统的图像处理方法依赖于图片的像素矩阵表示，有了矩阵之后，能做的事情就非常多了，例如二值化，阈值化，色彩均化，滤波（模糊/光滑），形态学开集和闭集，以及联通区域划分，图像金字塔等。这些处理方法在实际当中应用广泛，例如许多图片应用的滤镜/增强/变形效果,以及图片压缩。

上面这些只是针对单张图片的操作，随着照相技术的发展，图片越来越多，因此有了图片的分类以及基于内容的检索等实际的需求。传统机器视觉的方法或者说套路是，先针对问题和对特征的具体要求（例如希望特征具有旋转不变性等）设计一些特征抽取方法，有了特征之后，就能拿去喂给一些机器学习算法去做分类等进行后续的工作了。所以重点集中在了特征的设计这里。简单的特征，如颜色直方图，只是一个简单的统计描述，而其他常用的特征，如 Harris 角点，FAST 角点，图像梯度以及HOG, LBP(local binary pattern), SIFT 特征以及其变体 SUFT 和 ORB, haar 等，则经过了精心的设计，并且涉及一些诸如利用积分图像来优化计算的技巧，是传统计算机视觉的重要成果。

有了特征之后，能够解决的问题包括边缘检测/轮廓提取，图像分割，图片分类，人脸识别，图片拼接(image stitching)，视觉测距（包括单目视觉测距(Monocular Visual Odometry)和立体视觉测距(Stereo Visual Odometry)）等。

![图片拼接 来源 http://matthewalunbrown.com/autostitch/autostitch.html](../images/autostitch.png)

后来视频数据也多了起来。视频无非是一些连续的图片，因此图片处理技术很自然地被扩展到了视频处理上。当然，视频的动态特征也得到了特殊的对待，于是有了均值漂移、GMM（混合高斯模型）等背景建模的方法，以及利用光流法等实现物体的跟踪。

这之后，随着人工智能技术的崛起，深度学习大潮席卷了包括计算机视觉和自然语言处理在内的诸多领域，许多在之前无法有效解决的问题，比如图片语义分割、图片/视频内容描述、图片/视频问答等开始得到解决，许多新的问题，如图片自动生成、图片风格迁移等开始出现，并在深度学习的火炬下显示出无限可能，而传统的方法，那些人工设计特征的时代，似乎正在渐行渐远。



### Saliency
[MIT Saliency Benchmark](http://saliency.mit.edu/datasets.html)



### 人脸识别

[Rapid object detection using a boosted cascade of simple features](https://www.cs.cmu.edu/~efros/courses/LBMV07/Papers/viola-cvpr-01.pdf)

2001年 Paul Viola 和 Michael Jones 在CVPR上发表，文章中提出了三个要点：Haar-like 特征，AdaBoost 算法和 Cascade 结构，被称为 *Viola-Jones* 框架。



[Labeled Faces in the Wild](http://vis-www.cs.umass.edu/lfw/)


HMAX(Hierarchical Model and X)




### 图片检索

主要还是用哈希。用到的哈希方法大概分为两种，一种是数据相关的(因此也被称为 L2H, 即 learning to hash)，一种是数据无关的，比如局部敏感哈希(LSH, locality-sensitive hashing，ANN 的一种)。

L2H 既然是从数据中学习，自然又可以被分为两种：有监督的和无监督的。

- [Feature Learning based Deep Supervised Hashing with Pairwise Labels](http://arxiv.org/abs/1511.03855)

    采用用深度学习方法同时学习特征和哈希编码。



hyperlapse
延时视频

基于内容他的图片搜索(CBIR, content based image retrieval)传统上采用的都是特征匹配的方法，后来有了CNN之后，人们将网络的中间隐层激活子作为特征，结合最大池池化(max-pooling) 操作，也取得了不错的效果。

[particular object retrieval with integral
max-pooling of cnn activations, by Giorgos Tolias, et al., ICLR 2016, under review](http://arxiv.org/pdf/1511.05879v1.pdf)


### 资料
1. [Awesome Computer Vision](https://github.com/jbhuang0604/awesome-computer-vision)

本文参考
[面向机器视觉的深度学习资源汇总](http://www.open-open.com/lib/view/open1435818441450.html)
