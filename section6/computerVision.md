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



- [Neural storyteller](https://github.com/ryankiros/neural-storyteller)
    由图片生成小故事
