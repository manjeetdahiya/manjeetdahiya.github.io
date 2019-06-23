---
layout: post
title: Expectation and Various Summaries of a Distribution
---

The distribution of a random variable is quite detailed 
--- it contains all the probabilistic
information of the random variable.
Analogous to the summaries of the sample data sets like mean and variance,
we can define summaries of the probability distributions.
This post presents various summaries or properties of probability distributions.

### Expectation

Expectation of a random variable $X$, also called the *mean* or the *expected value*, is defined as:

Discrete: $
E(X) = \sum \limits_{x \in domain(X)} x f(x)
$

Continuous: $
E(X) = \int_{-\infty}^{\infty} x f(x)
$

Where $f(x)$ if _pf_ or _pdf_ or the random variable $X$.

Note that expectation is a property of the distribution.
Two different random variables with the same distribution will have the same expectation.

##### Theorem
* If the expectation exists for a random variable $X$, then the expectation of a random variable
  $Y = aX +b$, where $a$ and $b$ are constants, is: $E(Y) = a E(X) + b$.
* If $X_1$ and $X_2$ are two random variables such that their expectations exists, then the following holds:
  $E(X_1 + X_2) = E(X_1) + E(X_2)$.
* If $X_1$ and $X_2$ are two *independent* random variables such that their expectations exists, then the following holds:
  $E(X_1 X_2) = E(X_1)E(X_2)$.

### Variance

Variance of a random variable describes the spread of the distribution.
It measures how spread out the distribution is.
It is defined as:

$
Var(X) = E[(X - \mu)^2]
$

Where $\mu$ is $E(X)$.

Variance is usually denoted by $\sigma^2$. That is, $\sigma^2 = Var(X)$

Standard deviation ($\sigma$) is defined as the positive square root of variance.
It enables comparison with the random variable 
as it has the same units as the random variable.


##### Theorem
* $Var(X) = E[(X - \mu)^2] = E(X^2) - [E(X)]^2$
* If $Y = aX +b$, where $a$ and $b$ are constants, the $Var(Y) = a^2 Var(X)$.
* If $X_1$ and $X_2$ are two *independent* random variables, then the following holds:
  $Var(X_1 + X_2) = Var(X_1) + Var(X_2)$.
* If $X_1$ and $X_2$ are two random variables, then the following holds:
  $Var(X_1 + X_2) = Var(X_1) + Var(X_2) + Cov(X_1,X_2) + Cov(X_2, X_1)$. $Cov$ is defined next.
* In general, $Var(X_1+X_2+...+X_n)$ is given by the sum of all elements of
  the covariance matrix (defined later).

### Covariance
When dealing with a joint distribution of two random variables, covariance
describes how much these random variables are *linearly dependent* on each other.

Given two random variable $X$ and $Y$, the covariance of $X$ and $Y$ is defined as:

$$
Cov(X, Y) = E[(X -\mu_x)(Y -\mu_y)]
$$

Where $\mu_x = E(X)$ and $\mu_y = E(Y)$.

Covariance measures the expectation of the product of offsets from the respective means.
If both the random variables are simultaneously greater or smaller than the respective
means, then the covariance is positive.
If it is the other way round, then the covariance is negative.

Covariance measures the extent to which the random variable 
simultaneously take bigger or smaller values.

##### Theorem

* $Cov(X, Y) = E(XY) - E(X)E(Y)$

### Correlation

Covariance between two random variable could be impacted by the scale of the random
variables.
It does not allow comparison of the degree of dependence between two different pairs
of random variables.
Correlation is a measure that solves this issue. It is defined as:

$$
\rho (X, Y)= \frac{Cov(X, Y)}{\sigma_x \sigma_y}
$$

##### Theorem
* $-1 \le \rho(X, Y) \le 1$
* If $X$ and $Y$ are independent, then $\rho (X, Y) = 0$. The converse is not generally  true.
* $\mid \rho(X, aX+b) \mid = 1$, where $a$, $a \ne 0$ and $b$ are constants. If $a \gt 0$, then $\rho(X, aX+b) = 1$, else if $a \lt 0$, then $\rho(X, aX+b) = -1$.

Example of dependent variables with zero correlation:
Random variable $X$ and $X^2$ are clearly dependent, where X takes -1, 0, 1 with equal probabilities. However, $Cov(X, X^2) = 0$.
This example, shows that correlation/covariance does not capture *nonlinear* dependence.

### Covariance matrix

In case of random vector ($\textbf{X}$, of dimension $d$), 
or otherwise, a collection of random variables, we define
the notion of covariance matrix as:

$$
CovMat(\textbf{X}) = 

\begin{bmatrix}
\sigma_{11} & ... &\sigma_{1d} \\
... & ... & ... \\
\sigma_{d1} & ... &\sigma_{dd}
\end{bmatrix}
$$

Where $\sigma_{ij} = Cov(X_i, X_j)$. 

Another way to state:
$CovMat(X) = E[(X - \mu)(X - \mu)^T]$



##### Properties
* Since $\sigma_{ij} = Cov(X_i, X_j) = Var(X_i)$ for $i = j$, 
the diagonal of covariance matrix represents
the variances of the individual random variables.
* The matrix is symmetric across the diagonal as $\sigma_{ij} = \sigma_{ji}$.
* When the variables are independent, the covariance matrix is a
diagonal matrix as $\sigma_{ij} = 0$ for all $i, j | i \ne j$.