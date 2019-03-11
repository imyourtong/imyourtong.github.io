---
layout:     post
title:      Gender Inequality | 笔记分享 | Facebook上的女性用户影响了GDP吗？
subtitle:   
date:       2019-03-08
author:     imyourtong
header-img: img/home-bg-art.jpg
catalog: true
tags:
    - 论文
    - 视频

---


## 作者想说什么？

这篇论文讲了这样一个故事：

在传统的传播学中，有一个理论叫做“知识沟”，人与人之间因为获取信息的能力差距，所获得的知识量存在差异，这可能导致个人发展差距、经济差距、社会地位差距……在新时期互联网环境下，同样地存在着“数字鸿沟”，信息资源的差距除了影响个人，甚至已经扩展到了群体、国家层面。

那么，两个性别之间存在着这样的情况吗？世界经济论坛每年会发布《全球性别差距报告》中会衡量男女在经济、教育、政治、医疗上的差距，既然两性在经济上存在这样的差距，那么是否与男女在获取信息上的“鸿沟”有关呢？这样的鸿沟又怎样来测量呢？鸿沟-经济差距-性别不平等，这三者关系可以用模型来表示吗？

在这篇论文中，作者通过Facebook的营销接口抓取数据，建立了一个覆盖217个国家，超过14亿用户的匿名数据集。

![](https://ws4.sinaimg.cn/large/006tKfTcgy1g0wvfxkgenj30dq0bujsx.jpg)

数据的详细大小如下：

![](https://ws4.sinaimg.cn/large/006tKfTcly1g0wvgx9n7oj30io048q4c.jpg)

通过男女在Facebook上活跃度的差距作为衡量“知识沟”的重要方法，提出了一个名为FGD（Facebook Gender Divide）指标：

![](https://ws1.sinaimg.cn/large/006tKfTcgy1g0wvied1jqj30d607cjrv.jpg)

表示两个性别的活跃程度比，大于零说明男性更活跃，等于零说明男女活跃程度相等，小于零则说明Facebook上的女性更加活跃。（性别活跃人口/性别总人口）全球国家的FGD指标呈现大致如下：

![](https://ws2.sinaimg.cn/large/006tKfTcgy1g0wvjp484zj30x20d6ds1.jpg)

在提出这个指标之后，论文主要分为论证FGD有效性和建立相关模型两部分：

在论证有效性时，引用了GWI、Pew Global、Pew US三个数据调查的结果。

GWI：

是在2015年后两个季度和2016年前两个季度在34个国家投放了99338份问卷（做了估计数，适用于全球主体）问卷中有关于Facebook使用频率的问题，以此得到一个DAU数（活跃用户）即每天使用一次以上的用户在各个性别、年龄段中的加权比例。

Pew Global：

是在2016年春季，覆盖19个国家23462个小组成员，通过“你曾经使用过在线社交网络吗？”这个问题来测量SNS工具的渗透性。

Pew US：

是在2016年3月7日到4月4日，通过在1601份问卷中提问“你使用过Facebook吗？”，测量Facebook在不同年龄和性别中的使用率。

这这篇论文的附录中，作者给出了计算结果：

![](https://ws4.sinaimg.cn/large/006tKfTcgy1g0wvkqel6kj30vk0s8n7k.jpg)

这里面的计算除去了一些极异常值，如中国。于是我们可以得到结论：来自市场营销 API 的 Facebook 渗透率估计值与 GWI 和皮尤研究中心的高质量、有代表性的调查报告的价值具有可比性。

在研究性别差异时，结果是这样的：

![](https://ws1.sinaimg.cn/large/006tKfTcgy1g0wvla17w1j30uu0r87dc.jpg)

与Facebook 渗透率一样，我们可以得出结论，使用营销 API 对 FGD 的估计与 GWI 和 Pew 调查指标是一致的，这使得 FGD 的研究可以扩展到更多的国家。

作者同时衡量了在营销 API 和每个调查数据集中 FGD 之间的绝对差异，在进一步的分析中加入了对 Facebook 渗透率的控制，以确保结果不是营销 API 中渗透率和测量误差之间的关联产物。

同时这样的对比研究，作者也在其他社交网站（如ins/twitter/youtube……）中进行了复现，也得到中高级别的皮尔森系数。

在对年龄的研究中也采用了这样的方法得到了高而显著的皮尔森相关系数，我们可以得出结论，Facebook 营销 API 提供的数据在不同年龄段是一致的，但为了确保进一步的分析是可靠的，采取了两个行动:

1)在回归模型中添加了一个平均用户年龄控制；

2)按年龄分类分析，在每个阶层中使用相应年龄段的 FGD 测量值。


## 建模部分

对所有变量进行了rank transformation将衡量性别平等的变量和FGD的关系构建为一个线性模型：

![](https://ws4.sinaimg.cn/large/006tKfTcgy1g0wvmjh3q4j30vo0a479e.jpg)

Q是一个矩阵，包含每个国家在经济、健康、教育、政治上的性别平等指数，C包含控制变量。（如：互联网渗透率、收入不平等、总人口、FB渗透率、平均用户年龄）

下面的三个表依次是拟合的详细结果，用robust进行回归的结果，对异方差进行HC校正，这三者的结果定性相似，对异常值和异方差有较好的鲁棒性。

![](https://ws3.sinaimg.cn/large/006tKfTcgy1g0wvnid4gkj30u00v3tnp.jpg)
![](https://ws4.sinaimg.cn/large/006tKfTcgy1g0wvnvuonyj30w00eggsz.jpg)

接下来，作者将GDP和FGD的关系单独拿出来进行分析。发现两者呈现负相关，GDP则和互联网渗透率呈正相关，因此我们可以在之后的分析中用互联网渗透率代替GDP，这里也做了一个月度测量来观察稳定性。除此之外，还做了跨年龄组的稳定性分析。

![](https://ws3.sinaimg.cn/large/006tKfTcgy1g0wvovdyqaj30vk0n8n68.jpg)

然后作者建立起经济变化和FGD的关系模型：

![](https://ws4.sinaimg.cn/large/006tKfTcgy1g0wvpku7b9j30w80c2n2g.jpg)

得到：

![](https://ws3.sinaimg.cn/large/006tKfTcgy1g0wvq2a1j8j30vm0sy14b.jpg)


## 心得

Online social networks may lower the barriers that women have to access to informational resources and help to narrow the economic gender gap.

本期读书分享在b站有分享视频：[第谷读书会|论文|怎样用大数据做一个性别研究？](https://www.bilibili.com/video/av45672444)

### PS:在看这篇论文时一定要配合附录一起看。

