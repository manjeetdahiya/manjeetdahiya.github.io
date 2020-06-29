---
layout: post
title: Gradient Descent Extensions
---

Goal of extensions of gradient descents
such as Momentum, RMSProp and Adam
is to speedup gradient descent and address the challenges
faced by gradient descent algorithm. This post presents the challenges
and optimizations to handle the same.

### Challenges of gradient descent

* Learning rate: large value results in oscillations...smaller value is slow to converge
* Choosing a learning rate that is applicable to all the dimensions. --in presence of steeper dimensions.
* Saddle points
* Oscillations/noise of SGD.

### Momentum

What does it solve?

* It solves the problem when in one dimension the learning is quite slow
  and resulting in oscillations in the other dimensions.
* It also helps to minimize noise due to SGD.

$$
G_t = \beta G_{t-1} + (1 - \beta) \nabla L_{t}
\\
W_t = W_{t-1} - \eta G_t
$$

* $\beta \in (0, 1)$. Common value of $\beta$ is 0.9.
* There is an alternative equation used in literature without the factor $1-\beta$.
* It computes the exponential weighted moving average of the gradients.
* It also becomes important in the context of SGD, where the the gradients
  are noisy and averaging helps significantly. It dampens the oscillations.
* It helps navigate the ravines efficiently.
  Ravine is a volume where the gradient is steeper in a particular directions.
  Gradient descent in that case results in taking large number of steps as
  we cannot afford to have a large value of the learning rate, which could
  result in divergence in the steeper dimensions.
* Momentum solves this issue by having a large value of learning rate 
  in the dimension with less steeper and small value for the steeper dimension.
  The momentum equation is simply an average of the last few values of the gradients. The average in the steeper dimension is small because of the oscillation (average of negative and positive number) whereas the gradient in
  the other direction keeps adding to result in a large value in the slower dimension.
* Newtonian interpretation: One can thing of SGD/GD as a person walking down
  the hill steadily taking constant size steps. GD+Momentum can be considered
  as a heavy ball rolling down gaining momentum in the downward direction and
  dampening the oscillations and noise in the other directions.

### RMSProp (Root-mean squared prop)

$$
S_t^i = \beta S_{t-1}^i + (1 - \beta) (\nabla L_{t}^i)^2
\\
W_t^i = W_{t-1}^i - \frac{\eta \nabla L_{t}^i}{\sqrt{S_t^i} + \epsilon}
$$

* Solves the same problem as Momentum. It dampens the oscillations in the direction of steep gradients.
* The name comes from the fact that it computes root-mean squared of the gradients. In fact, it computes 
  EWMA of the square of the gradients.
  The first equation represents the EWMA of the square of the gradients.
* The equation is written for each dimension. Index $i$ represents the dimension.
* $\nabla L_{t}^i$ is the ith component of the gradient. That is, $\nabla L_{t}^i = \frac{\partial L(W)}{\partial W^i}$
* In the second equation, the gradient is divided by square root of $S_t^i + \epsilon$.
* A small value $\epsilon$ is added just for the sake of numerical stability. 
  It helps avoid division by a zero. A common value of $\epsilon$ is $10^{-8}$
* In the direction of steeper gradients (oscillating direction) $S_t^i$ would be high and would result
  in a small change in the second equation because of the division by the same.
* On the other hand, in the slow moving direction, $S_t^i$ would be small and would result in a larger 
  change in this direction as we can choose a bigger value of learning rate in the second equation.

### Adam

Momentum and RMSProb both have their limitations.
Adam is a more robust optimization; it combines Momentum and RMSProb both.

$$
G_t = (\beta_1 G_{t-1} + (1 - \beta_1) \nabla L_{t})* \frac{1}{1-\beta_1^t}
\\
S_t^i = (\beta_2 S_{t-1}^i + (1 - \beta_2) (\nabla L_{t}^i)^2)* \frac{1}{1-\beta_2^t}
\\
W_t^i = W_{t-1}^i - \frac{\eta G_t^i}{\sqrt{S_t^i} + \epsilon}
$$

* Adam: Adaptive moment estimation.
* Combines Momentum and RMSProp.
* It also performs bias correction while computing EWMA,
  the multiplication terms in the first two equations encodes the same.
* Common value of $\beta_1$ is 0.9.
* Common value of $\beta_2$ is 0.999.
* Common value of $\epsilon$ is $10^{-8}$.

### Learning rate decay

* It is good idea to decay the learning rate with iterations to avoid oscillations while convergence.
* It will make sure that the oscillations are bound to a tighter region. Hence, resulting in a better 
  solution.
* There are many ways to achieve the same; below are a few methods:

$$
\eta = \frac{\eta_0}{1+decayrate * epoch}
$$

$$
\eta = \frac{k}{\sqrt{epoch}} \eta_0
$$

$$
\eta = 0.95^{epoch} \eta_0
$$

$$
\eta = 0.95^{t} \eta_0
$$

<!-- ### Adagrad

### Adadelta -->

