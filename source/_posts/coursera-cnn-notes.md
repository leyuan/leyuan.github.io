---
title: coursera-cnn-notes
date: 2018-02-21 23:46:35
tags:
math: true
---

### Week One

### Padding Convolution(one of convolution block)

6x6 matrix, filter size 3x3 => 4x4 matrix

problems:
1. image is shrinking everytime so fast
2. corner pixel only used once, middle pixel used too much

So paddings are needed. Valid Padding: No Padding

Same Padding: Pad so output size is the same as the input size, to make this happen the following equations needs to be satisfied

$n + 2p -f +1 = n$

$p = \dfrac{f-1}{2}$

By convention f is almost always `odd`

### Strided Convolution(one of convolution block)

Summary of convolutions

n x n image // f x f filter // padding p // stride s

After convolution:

$\left \lfloor{\dfrac{n+2p-f}{s} + 1}\right \rfloor$ x $\left \lfloor{\dfrac{n+2p-f}{s} + 1}\right \rfloor$

### Convolutions Over Volume

Image has 3 channels R, G, B, fitlers have 3 channels as well.

If rgb filter is designed carefully, it can be used to only detect vertical red edge or generally vertical edges.

On top of above, multiple filters can be stacked together to perform different purpose of detections.

### One Layer of a Convolutional Network

If layer l is a convolution layer:

$f^{[l]}$ = fitler size

$p^{[l]}$ = padding

$s^{[l]}$ = stride

$n_c^{[l]}$ = number of filters

Each filter is: $f^{[l]} \times f^{[l]} \times n_c^{[l-1]}$

Activations: $a^{[l]}$

Weights: $f^{[l]} \times f^{[l]} \times n_c^{[l-1]} \times n_c^{[l]}$

bias: $n_c^{[l]}$ - (1, 1, 1, $n_c^{[l]}$)

Input: $n_H^{[l-1]} \times n_W^{[l-1]} \times n_c^{[l-1]}$

Output: $n_H^{[l]} \times n_W^{[l]} \times n_c^{[l}$

$n_{H/W}^{[l]} = \left \lfloor{\dfrac{n_{H/W}^{[l-1]} +2p^{[l]} - f^{[l]}}{s^{[l]}} + 1}\right \rfloor$

### Simple Convolutional Network Example

![image](images/xxx)

Types of layer in CNN

- Convolution
- Pooling
- Fully Connected

### Pooling Layer

- Max pooling

A bigger number likely represents the feature that we want to detect, the max operator captures the feature in the particular region.

Hyperparameters, NO parameters to learn.

- Average Pooling

Collapse the features into an average number.

### Why Convolutions

**Parameter Sharing**: # of parameters in a Conv layer is much less than the # of parameters in a FC layer. A feature detecor(such as vertical edge detector) that's useful in one part of the image is probably useful in another part of the image.

**Sparsity of connections**: In each layer, each output value depends only on a samll number of inputs. For a particular area, the rest part of the image does not contribute to its features.





---