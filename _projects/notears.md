---
layout: page
title: NOTEARS TF2
description: an implementation of the NO-TEARS Bayesian network optimization algorithm in Tensorflow 2.
img: 
importance: 3
category: work
---
A [Python package](https://github.com/cnellington/notears-tensorflow2) for plug-and-play DAG and Bayesian network optimization
using the NO-TEARS algorithm.


[NO-TEARS](https://arxiv.org/abs/1803.01422) 
is a unique use of the [matrix exponential](https://en.wikipedia.org/wiki/Matrix_exponential)
that creates a differentiable scoring function for the 
acyclicity of a graph, providing the first smooth loss 
for optimization-based learning of DAGs and Bayesian networks.
This is the bedrock for my work on
meta-learning approaches for personalized
Bayesian network inference. 