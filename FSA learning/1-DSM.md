# Deep Specification Mining

[TOC]



## Contributions

1. We propose DSM (Deep Specification Miner), **a new specification mining algorithm** that utilizes test case generation, deep learning, clustering, and model selection strategy to infer FSA based specifications. To the best of our knowledge, we are the first to use deep learning for mining specifications.
2. We evaluate the effectiveness of DSM on 11 different target library classes. Our results show that our approach outperforms the best baseline by a substantial margin in terms of average F-measure.
3. We propose a **technique that employs a FSA inferred by DSM to construct a more comprehensive sandbox** that considers execution context of sensitive API methods. Our evaluation shows that our proposed technique can outperform several baselines by a substantial margin in terms of either True Positive Rate or False Positive Rate.

## Problem Set (Input, Output):

### 算法1：迹的采样：

**Input**: 执行迹的集合S，大小为N

**Output**：被选择的执行迹子集O

启发式算法 
S：迹的集合
P：存储以下对
定义对(a,b) 其中 a 和 b 是至少在一个迹中一起出现的方法
O：包含选择的迹，一开始为空集
过程：
1. 选择O中不存在的对(a,b)
2. 查找不在O中的最短迹$S_i$，但$a,b\in S_i$
3. 将$S_i$加入O，将(a,b)从P中删除

**前缀树接受器（PTA）**：

- PTA 是通过将序列的所有前缀作为状态创建的树状确定性有限自动机 (DFA)
- PTA 只接受构建它的序列

### 特征提取

对以下两种类型的特征感兴趣：

- 捕获了在到达状态S之前的methods ？
- 捕获了即将要被其他阶段调用的methods



### 算法2：预测FSA的精确度

**Input**: 一个有限状态自动机M，一个训练集Data

**Output**: M的预测精度

#### 聚类方法

k-means 和 分级群聚 on PTA’s states

#### 模型选择

启发式算法 算法2



## Example

从图 3 部分显示的 PTA 中，我们对 PTA 的每个状态进行特征提取。然后，我们将这些具有提取特征的状态输入到聚类算法（即 k-means 和层次聚类）中，以合并相似的状态。如果 MAX_CLUSTER 被确定为 20，那么这两种聚类算法总共将构建 38 个 FSA。图 4 显示了 k-means 输出的 19 个 FSA 中的 2 个。接下来，我们对这些 FSA 进行模型选择，以选择具有最高预测 F 度量的模型。


## motivation

Formal Specifications?正式规范
need skill and time
Algorithms that infer finite-state automaton (FSA) based specifications from execution traces

## challenge



## approach



## experiment

### Dataset



## References
Ivo Krka, Yuriy Brun, and Nenad Medvidovic. 2014. Automatic mining of specifications from invocation traces and method invariants. In Proceedings of the 22nd ACM SIGSOFT International Symposium on Foundations of Software Engineering, (FSE-22), Hong Kong, China, November 16 - 22, 2014. 178–189.

### SOTA(Sate-Of-The-Art)

## What-can-improve / What-didn’t-do

作为未来的工作，我们计划通过将可能不变量的信息集成到我们基于深度学习的框架中来进一步提高 DSM 的有效性。我们还计划使用 EvoSuite [16] 和许多其他测试用例生成工具来生成更全面的训练跟踪集，以提高 DSM 的有效性。此外，我们计划通过考虑除 k-means 和层次聚类之外的更多聚类算法来改进 DSM，尤其是那些不需要输入聚类数量的算法（例如 DBSCAN [15] 等）。最后，我们计划用更多的类和库来评估 DSM，以减少对外部有效性的威胁。

