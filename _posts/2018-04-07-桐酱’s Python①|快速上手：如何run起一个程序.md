---
layout:     post
title:      桐酱’s Python①|快速上手：如何run起一个程序？
subtitle:   小白教程No.1
date:       2018-04-07
author:     tongchen
header-img: img/post-bg-cook.jpg
catalog: true
tags:
    - python
---

## 背景

0基础并疯狂吹嘘自己学习能力的李桐辰接到导师要求用Python进行数据分析！

## 代码和数据来源

>Vosoughi, Soroush, Deb Roy, and Sinan Aral. "The spread of true and false news online." Science 359.6380 (2018): 1146-1151.

### 前期准备 

在向作者申请到了代码和数据之后，着手安装PyCharm Community，因为安装的是3.4的版本，但代码要求2.7的环境，因此首要任务是配置一个python2.7的虚拟环境，并按照readme.txt的要求，安装packbag们。

→在此感谢pip提供一键安装方案（鞠躬～

![](https://ws2.sinaimg.cn/large/006tKfTcgy1g0m72vcijbj311i0m4wox.jpg)

在建立好project，配置成功（看到一堆setting的第一反应是倒吸一口冷气，觉得自己的学术之路怕是要困在英语上了）之后，遇见了all pythoners all !!! all !!! 都会遇见的

### 编码问题

emmmmm……tough life,用万事开头难鼓励自个儿……

在这里简单为以后可能忘了这个知识点的自己note一下：

![](https://ws3.sinaimg.cn/large/006tKfTcgy1g0m76hl9mfj310i0h80we.jpg)

ASCII：查询字符和ASCII码对应关系可查看https://www.ascii-code.com/

EASCII：在ASCII基础上扩展而来，如CP437是WIN系统中使用的字符编码。

GBK：中国发布，英文字符用1个字节，汉语字符用两个字节标识。

Unicode：简称UCS，两种格式（UCS-2和UCS-4）,世界上的任何一个字符都可以用一个Unicode 编码来表示。局限性：浪费空间；只规定了如何编码，没规定如何传输、保存这个编码。

UTF-8是Unicode的一种实现方式，是一种变长的字符编码（1-4字节）。

Python的默认编码是ASCII，要在源代码总支持非ASCII字符，必须在源文件的第一行或者第二行制定编码格式。

> coding=utf-8 

### 开始运行

接下来为了在UTF-8的编码环境下运行程序，需要将win的编码和Pycharm中的编码改成UTF-8。

如何在win中修改呢？
1.打开注册表编辑器（regedit）

![](https://ws1.sinaimg.cn/large/006tKfTcgy1g0m7b9j818j31100iwdp5.jpg)

2.HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Command Processor，根据这个路径进行查找。

3.然后“右键-新建”，选择“字符串值”，“名称”列填写“autorun”, 数值数据填写“chcp65001”，即可永久修改，结果如下，命令提示符里显示当前代码页为UTF-8。

![](https://ws2.sinaimg.cn/large/006tKfTcgy1g0m7d5w4i0j31aq0owqie.jpg)

修改Pycharm中的编码环境？

![](https://ws1.sinaimg.cn/large/006tKfTcgy1g0m7efkwrdj31ae0toww5.jpg)

将图中显示UTF-32的部分改成UTF-8即可！

Soooooooo easy！然后就可以run啦！

 

