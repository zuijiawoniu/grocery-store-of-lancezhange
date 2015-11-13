# 计算机视觉专题

机器视觉领域的顶会
- CVPR 国际计算机视觉和模式识别会议
- ICCV 国际计算机视觉大会
- ECCV 欧洲计算机视觉大会

传统的机器视觉抽取的特征有
- FAST 角点
- Harris 角点

#### 视觉测距
参考 [VO from Scratch - a tutorial for beginners](http://avisingh599.github.io/vision/visual-odometry-full/)，写的很清晰


- 单目视觉测距(Monocular Visual Odometry)

    单个摄像头
    - [MVO using OpenCV](http://avisingh599.github.io/vision/monocular-vo/)
- 立体视觉测距(Stereo Visual Odometry)
    多个摄像头



#### 图片拼接(Image Stitching)

- 随机抽样一致算法(RANSAC)

![图片拼接 来源 http://matthewalunbrown.com/autostitch/autostitch.html](../images/autostitch.png)


#### 图片问题回答

参见[问答系统专题](./qa.md)


#### 图片描述(Image Caption)

图片描述是较难的，因为要对场景做准确的理解

- [MS COCO Captioning Challenge](http://mscoco.org/dataset/#captions-challenge2015)

    比赛于2015年4月开始，5月结束（但测评服务目前仍然开放），7月份在 CVPR 2015 Large-scale Scene Understanding workshop 宣布结果。采用人工裁判，排在第一的还是人，后面两名则分别来自谷歌和微软（打了个平手）。

- [Neural Storyteller](https://github.com/ryankiros/neural-storyteller)

     所谓的看图说话。



### 视频描述
视频内容描述是图面内容描述的自然延伸，在视频搜索，人机交互，为盲人讲述内容等场景中均有切实的需求。

图片的内容描述，最后生成的句子的长度是不定长的，在视频描述中，多了一个不定长的变量：图片帧的个数。此外，现实视频中的物体繁多，场景多样，动作各异，这为视频内容描述带来了不小的困难。如何识别出最主要的内容也是难点，因为我们只想描述视频中最主要的部分，而不是面面俱到。

LSTM 模型的成功。

后来又加入了 attension, 

基准数据集
1. MSVD(microsoft video description corpus)
2. MPII-MD(MPII movie description dataset)
3. M-VAD(montreal video annotation dataset)

- [LSMDC 2015](https://sites.google.com/site/describingmovies/)

    The Large Scale MOvie Description Challenge, at ICCV 2015.

### 图片检索

主要还是用哈希。用到的哈希方法大概分为两种，一种是数据相关的(因此也被称为 L2H, 即 learning to hash)，一种是数据无关的，比如局部敏感哈希(LSH, locality-sensitive hashing，ANN 的一种)。

L2H 既然是从数据中学习，自然又可以被分为两种：有监督的和无监督的。

- [Feature Learning based Deep Supervised Hashing with Pairwise Labels](http://arxiv.org/abs/1511.03855)

    采用用深度学习方法同时学习特征和哈希编码。

