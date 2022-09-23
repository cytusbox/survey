# Decision-Guided Weighted Automata Extraction from Recurrent Neural Networks

[TOC]



## Contributions

1. an algorithm for WFA extraction from RNN classifiers with better scalability and precision;(可扩展性和精度) 
2. three important techniques including the configuration guidance for state abstraction by identifying decision patterns, the state composition to counteract contextual loss, and the synonym transition to circumvent missing dynamics of new data; 
3. an implementation of the algorithm and evaluations over 15 benchmarks, including comparisons with the state-of-the-art (Weiss, Goldberg, and Yahav 2019).

## Problem Set (Input, Output):

加权自动机提取

RNN



带权有限自动机(WFA)：元组$A=(Q,\Sigma,(E_\sigma)_S{\sigma \in \Sigma},I,T)$

Q：状态的集合

Eσ：过渡矩阵，大小为|Q|x|Q|

T：最终向量

### 算法1：从RNN中提取出WFA

**input**：目标RNN，输入的序列

**output**：提取的WFA



**k-DCP**: k 决策置信模式

## Example

我们展示了使用我们的方法为新闻分类任务提取的 WFA，并展示了它如何总结和解释 RNN 学到的知识。总共有7个标签，包括商业、美国、健康和其他四个。我们假设输入序列 w = [“recipes”, “for”, “health”, “roasted”, “leeks”]，其标签是健康。这里我们关注关键词“健康”，看看 RNN 是否也将其视为健康标签的重要含义。提取的 WFA 包含 42 个状态。为了简化表示，我们只保留读取“健康”后概率分布受影响最大的三个状态。我们假设“健康”之前状态的概率分布是 I·E~recipes~·E~for~=[0.89(q0), 0.03(q1), 0.0(q2)]。显示了令牌“健康”的转移矩阵在等式（1）中。消费“健康”后更新的概率分布为[0.0(q0), 0.54(q1), 0.44(q2)]。为了更好地理解“健康”对预测的影响，我们在最终矩阵（由每个标签的最终向量形成）中显示与三种状态相关的行。对于状态 q0、q1 和 q2，最高预测的概率为 [0.47(US), 0.30(business)], [0.40(US), 0.29(business), 0.25(health)] 和 [0.94(health), 0.03（业务）]。我们可以看到 q2 极有可能产生标签健康。直观上，转移矩阵代表了该分类下“健康”的具体语义。 q2是“健康”转移图中的吸收状态，其他状态转移到q2的概率也很大。如此解读，我们知道，RNN 学习到的“健康”语义基本上符合人类的感知。


## motivation



## challenge



## approach



## experiment

### Dataset



## References


### SOTA(Sate-Of-The-Art)



## What-can-improve / What-didn’t-do


