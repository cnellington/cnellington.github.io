---
layout: post
title:  Evolution of Personalized Models
date:   2022-07-19 10:00:00
description: Unifying a statistical lineage
tags: math machine-learning statistics personalization
categories: research
---
*This list is not complete, but my end goal is to make it comprehensive.
If there is a model you don't see here that belongs in the set of "principal equations" below, please drop me a line.
My email can be copied using the icon on the main page.*


When observed data comes from highly individual, sample-specific models,

$$ X_i \sim P(X; \theta_i) $$

how can we recover $$N$$ sample-specific parameter estimates $$\{\widehat{\theta_i}\}_1^N$$ with just $$N$$ samples? 


Recently, I've been working on a survey of personalized modeling methods that answer this question with various assumptions about the relationships within a set models.
This interesting lineage of statistics has had sporadic contributions over its lifetime, and is rarely viewed as a single family of methods.
I'm writing this survey to unify this lineage and to raise awareness -- especially among clinicians and biologists -- that there is a suite of statistically-grounded methods for inferring personalized models that are well-aligned with our understanding of many real biological systems, while requiring little more effort to apply than classic subpopulation/cohort models.


### 0. Subpopulation and Cohort Models
First, an explanation of subpopulation and cohort models and their issues.
We will assume that the parameters $$\theta$$ for our model of interest have some log-likelihood function $$\ell(X; \theta)$$ over the data $$X$$.
For some subpopulation or cohort $$c$$, we can model this cohort with a generic estimator, maximizing the likelihood of the cohort model on the cohort data.

$$ \widehat{\theta_c} = \arg\max_{\theta_c} \ell(X_c; \theta_c) $$

This assumes that each subpopulation or cohort is homogeneous, having the same underlying model.
However, in many cases biological mechanisms are extremely heterogeneous and it would better align with our understanding if model estimates reflected the differences between samples.

# Personalized models
From here onward, I **very briefly** outline an assumption and a principal equation that applies this assumption to recover $$N$$ models from $$N$$ samples. I keep these equations simple to highlight the assumption-model relationship in each case.

## Context-informed models
Context variables like time or location (which we call *covariates*) can often explain model variation.

### 1. Classic varying-coefficient models
Assumption: models with similar covariates have similar parameters (more formally: parameters are smooth over covariates)

$$ \widehat{\theta}_0, ..., \widehat{\theta}_N = \arg\max_{\theta_0, ..., \theta_N} \sum_{i, j} \frac{K(c_i, c_j)}{\sum_{k} K(c_i, c_k)} \ell(x_j; \theta_i) $$

Where $$K(c_i, c_j)$$ is a similarity metric, usually a kernel.

Example: [Kolar, Mladen et al. “Estimating Time-Varying Networks.”](https://doi.org/10.1214/09-AOAS308)

### 2. Linear varying-coefficient models
Assumption: parameters vary linearly with covariates. Stronger than the classic assumption but highly interpretable. This allows the relationship between covariates and parameters to itself be parameterized. 

$$ \widehat{A} = \arg\max_A \sum_i \ell(x_i; A c_i) $$

$$\widehat{\theta}_0, ..., \widehat{\theta}_N = \widehat{A} C^T$$

Example: [Fan, Jianqing, and Wenyang Zhang. “Statistical Estimation in Varying Coefficient Models.”](https://doi.org/10.1214/aos/1017939139)


### 3. Contextualized Models
Assumption: parameters are some function of context, but make no assumption on the form of that function. 

$$ \widehat{f} = \arg \max_{f \in \mathcal{F}} \sum_i \ell(x_i; f(c_i)) $$

$$\widehat{\theta}_0, ..., \widehat{\theta}_N = \widehat{f}(C)$$

[Al-Shedivat, Maruan, et al. “Contextual Explanation Networks.”](https://doi.org/10.48550/arXiv.1705.10301)


## Latent-structure Models
These methods discover underlying structures in the data that guide model learning.


### 4. Partition models
Assumption: parameters can be partitioned into homogeneous groups over the covariate space, but make no assumption about where these partitions occur. Partition model estimators are most often utilized to infer abrupt model changes over time.

$$ \widehat{\theta}_0, ..., \widehat{\theta}_N = \arg\max_{\theta_0, ..., \theta_N} \sum_i \ell(x_i; \theta_i) + \sum_{i = 2}^N \text{TV}(\theta_i, \theta_{i-1})$$

Where the regularizaiton term might take the form 
$$\text{TV}(\theta_i, \theta_{i - 1}) = |\theta_i - \theta_{i-1}|$$

Example: [Kolar, Mladen et al. “Estimating Time-Varying Networks.”](https://doi.org/10.1214/09-AOAS308)
 

## Context-informed latent-structure models
These methods use principals from both context-informed and latent-structure methods.

### 5. Distance-matching models
Assumption: there is a transformation of the context space where distance in the transformed space is equal to the similarity between models. 
This uses the similar-context-similar-parameter assumption from varying-coefficient models, but also imposes a different-context-different-parameter assumption that doesn't directly follow the first.

$$ \widehat{\theta}_0, ..., \widehat{\theta}_N = \arg\max_{\theta_0, ..., \theta_N, D} \sum_{i=0}^N \prod_{j=0 s.t. D(c_i, c_j) < d}^N \ell(x_j; \theta_i) P(\theta_i ; \theta_j) $$

Where $$D(c_i, c_j)$$ is a learnable distance metric.

Example: [Lengerich, Benjamin, et al. “Learning Sample-Specific Models with Low-Rank Personalized Regression.”](https://doi.org/10.48550/arXiv.1910.06939)

Thanks for reading!

*This list is not complete, but my end goal is to make it comprehensive.
If there is a model you don't see here that belongs in the set of "principal equations" below, please drop me a line.
My email can be copied using the icon on the main page.*
