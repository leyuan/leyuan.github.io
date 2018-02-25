---
title: ROC, AUC, True Positive, False Positive
date: 2018-02-22 20:43:51
tags:
math: true
---

Explaination drawn from this youtube video -
[youtube source](https://www.youtube.com/watch?v=OAl6eAyP-yo)

###True Positive

when the actual classification is positive, how often does the classifier reports positive

$\dfrac{true \space positive}{all \space positives}$

###False Positive

when the actual classification is negative, how often does the classifier incorrectly predict positive

$\dfrac{flase \space positive}{all \space negatives}$

### ROC - Receiver operating characteristic -

A graph that show `true positive rate` against `false positive rate` at different threshold setting. It can be used to select possibly optimal models and discard the suboptimal ones. ROC analysis is related in a direct and natural way to cost/benefit analysis of diagnostic decision making.

### AUC - Area under curve

Area under the ROC curve; how well the classifier separate the ditribution

0.5 => random guessing // 1.0 => perfect

### Some properties

1. AUC is useful when the distribution is highly unbalanced
2. ROC can be extended to multiple classifiers
3. How to set the threshold is a business decision, the tradeoff between `MAXIMIZING true positive` vs `MINIMIZING false positive`
