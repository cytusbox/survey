# Neuralizing Regular Expressions for Slot Filling

[TOC]

## Contributions

1. We propose an approximate FST inference algorithm and unfold it as a neural model that resembles bidirectional RNN models for sequence labeling.
2. We conduct our experiments on three popular SF datasets involving two domains and two languages. Results show that our model has superior performance on zero-shot and low-resource settings compared with all the previous methods and remains competitive on rich-resource settings.

## Problem Set (input, output)

输入：离散迹 

输出：序列标注  

从正例迹和负例迹中学习Finite-State Transducer对迹进行标注。



### Example

We show an example FST in Fig. 2. The input “flights from New York to Dallas” can be accepted by the FST, and the accepting path indicates a state sequence [q0, q0, q1, q2, q2, q3, q3] and output sequence [l, l, B-fr.city, I-fr.city, l, l].



## approach



### RE to FST

等价性：

1. RE matches a sentence if and only if the corresponding FST has at least one accepting path; 
2. the output sequence of the FST matches the content captured by the RE.

定理A.1：FST(input: $\Sigma$, output: $\Gamma$) <=> NFA (input: $\Sigma \times \Gamma$)

定理A.2：



### FST to i-FST(independent-FST)