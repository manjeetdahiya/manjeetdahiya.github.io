---
layout: post
title: Gradient Descent Variants
---

### Standard gradient descent

Standard gradient descent is also called batch gradient descent.
It updates the parameters using the complete training 
dataset in one go.
It computes the gradient by using all the training examples and then
updates the parameters (called back propagation in case of deep learning). 
This constitutes an epoch of the training.

Let us formally describe the same.
Given a loss function $L$ and the ith training example $X_i$ 
(input variables/features),
the loss is written as $\sum \limits_{i=0}^m L(X_i)$.
Here $m$ is the number of training samples.

The gradient descent parameter update equation is:

$$
W_t = W_{t-1} - \eta \nabla (\sum \limits_{i=0}^m L(X_i))
$$

* $W_t$ is the parameters at epoch $t$.
* $\eta$ is the learning rate.
* The number of changes in parameters per epoch is 1.

### Stochastic gradient descent

$$
W_t = W_{t-1} - \eta \nabla L(X_i)
$$

* The number of changes in parameters per epoch is m.
* Suitable for online training.

### MiniBatch gradient descent

$$
W_t = W_{t-1} - \eta \nabla (\sum \limits_{i=0}^b L(X_i))
$$

* Best of both worlds.
* $b$ is the mini batch size.
* The number of changes in parameters per epoch is m/b.
* Suitable for online training.

<!-- ### Coordinate descent

### Subgradient -->