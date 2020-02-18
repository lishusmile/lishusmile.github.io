--- 
layout: post
title: MRF and CRF 
category: PGM
tags: 
keywords: MRF CRF
description: 
--- 


# CRF

条件随机场(Conditional random fields)，是一种判别式图模型，因为其强大的表达能力和出色的性能，得到了广泛的应用。从最通用角度来看，CRF本质上是给定了观察值集合 (observations)的马尔可夫随机场（MRF）。

# RF

随机场可以看成是一组随机变量的集合，这些随机变量之间可能有依赖关系。

# MRF

Markov性质是指，对Markov随机场中的任何一个随机变量，给定场中其他所有变量下该变量的分布，等同于给定场中该变量的邻居节点下该变量的分布。

# MRF and CRF 

在分类器中有两种概率类型，一种是 generative models， 一种是 discriminative models. MRF 便是generative models， CRF 属于 discriminative models。 这里举个例子简单说明这两者的区别。有两个随机时间A和B。 描述A和B同时发生的概率P(A,B)便是generative models。 而条件概率P(B|A)表示discriminative models， 表示在A发生的条件下B发生的概率。CRF和MRF相比优势在于，CRF不需要对A事件进行描述，直接关注于研究对象B事件，这样在一定程度上简化了问题。在图像分割中，A事件一般是一幅图片，而B事件是最终的分割结果，即每个像素的标号值。MRF模型需要得出图片和每个像素标号的联合统计结果，这个显然很困难。 而CRF是基于图片直接得出标号的统计结果，大大简化了问题。

MRF关注联合概率分布，CRF关注条件概率分布。所以MRF属于生成模型，而CRF属于判别模型。因此个人认为它们之间的差别主要是生成模型与判别模型的差别。生成模型本身比判别模型描述能力强，因为联合概率分布可以推导出条件概率分布：P(Y|X)=P(X,Y)/P(X),而判别模型收敛比较快。

# reference 

https://www.cnblogs.com/ironstark/p/5285410.html
https://www.jianshu.com/p/55755fc649b1
https://www.quora.com/What-is-the-difference-between-Markov-Random-Fields-MRFs-and-Conditional-Random-Fields-CRFs-When-should-I-use-one-over-the-other