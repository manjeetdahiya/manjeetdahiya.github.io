---
layout: post
title: Exponential Weighted Moving Average
---

Given a series of numbers we can approximate the moving average of the last $k$ numbers
using a technique called *exponential weighted moving average* (EWMA).
It requires very few computations and does not need to store the last $k$ numbers.

EWMA has many applications, it is used as a form of exponential smoothing in time series data, and
it is used in the different variants of gradient descent like Momentum and Adam.
Congestion control in computer networking
and job scheduling in operating systems are other areas where it is used.

#### Exponential Weighted Moving Average (EWMA)

Given a series $v_t$, the moving average of the same, denoted as $A_t$, is computed
by the following equations:

$$
A_1 = v_1
\\
A_t = \beta A_{t-1} + (1-\beta) v_t
$$

Here $\beta \in (0, 1)$.
At $t = 0$, the average is $A_1 = v_1$, and for the subsequent values of $t$,
the average is computed by the second
equation.

Expanding the above equations recursively results in:

$$
A_t = \frac{(\beta^{t-1} v_1 + \beta^{t-2} v_2 + \beta^{t-3} v_3 +... + v_t)}{1/(1-\beta)}
$$

The value of the average at $t$ is such that the contribution of the recent values is
more than the older values.
And the contribution of the older values decreases exponentially.
The denominator approximates the sum of the weights.
The denominator is equivalent to the sum of the weights when $t \rightarrow \infty$.

The value of $\beta^{t}$ becomes very small after a certain value of $t$ (recall $\beta < 1$).
Thus, one can approximate the number of entries the moving average is representative of by using
the equation $(1-\epsilon)^{1/\epsilon} = 1/e$. 
Substituting $1-\epsilon$ for $\beta$ we get $(\beta)^{1/1-\beta} = 1/e$ ($e = 2.7$, the base of natural logarithm).
That is, at $t = 1/1-\beta$ the contribution of the value becomes almost one third and can be ignored.
One can say that $A_t$ is approximately the average over the last $\frac{1}{1-\beta}$ entries.

For the value of 0.9, it approximates the average over the last 10 entries and for 0.98, it approximates over 50 days.

Another way to understand the same is that for higher $\beta$ more weight
is given to the older values than the current entry.
A higher value of $\beta$ results in a smoother curve. 
However, it also makes it slow to adapt to the change due to the recent entries.

Note that EWMA is not exactly the moving average over the window of last k elements --
it is a weighted average over 
all the values seen.
The advantage of EWMA is its simple implementation
and requirement of a single value to store the moving average.
This is also the reason why this technique is preferred at a hardware level.

#### Bias correction

The base case of the EWMA equation is $A_1 = v_1$, and in the beginning the average
would be biased towards $v_1$ because $1-\beta$ is very small. 
To resolve the same, one can have the initialization as $A_0 = 0$ and then
correct the bias towards zero by dividing $A_t$ by $1 - \beta^t$. 
The value of $1 - \beta^t$ is small in the beginning and later approaches to one, hence,
the effect of the bias correction happens only in the beginning.
 
The final equation after bias correction is:

$$
A_0 = 0
\\
A_t = \frac{\beta A_{t-1} + (1-\beta) v_t}{1-\beta^t}
$$

When $t$ is small $A_t$ is inflated and when $t$ is large the denominator just becomes almost 1 and there is no effect of it.
