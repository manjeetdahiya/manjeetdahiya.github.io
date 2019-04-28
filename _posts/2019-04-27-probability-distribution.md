---
layout: post
title: Probability Distribution
---

This post presents the definition of probability distribution and cumulative distribution.

### Distribution of a Random Variable

We have probabilities of the different outcomes of an experiment, consequently, we get the probabilities of the different values that an associated random variable takes.
The distribution of a random variable ($X$) is a *collection* of probabilities of events of form $\{X \in C\}$, for all possible subsets $C$ of real numbers.
In simpler terms, the distribution of a random variable gives the probabilities of all possible values (including ranges) taken by a random variable.

A discrete distribution is defined in terms of probability function (_pf_), which also called probability mass function. For continuous random variables, distribution is defined in terms of probability density function (_pdf_). Thus, a _pf_ or _pdf_ helps define the distribution of a random variable. A summation or integration can be used to compute the same.

* Discrete: $Pr(X \in C) = \sum \limits_{x_i \in C} f(x_i)$
* Continuous: $Pr(X \in C = [a, b]) = \int_{a}^{b} f(x) dx$

Note: $Pr(X = c)$ is $0$ for any $c$ in case of a continuous random variable. 
The reason is that the area/integration is zero, 
another explanation is that the continuos random variable takes infinite number of values, 
the probability of taking a particular value is zero. 
However, the probability of ranges would turn out to be non-zero because of integration over a bigger range.

All _pf_ and _pdf_ must satisfy following conditions to obey
[the axioms of probability]({{ site.baseurl }}{% post_url 2019-01-19-the-axiomatic-definition-of-probability %}):

* Discrete: $\sum \limits_{x_i \in domain(X)} f(x_i) = 1$
* Continuous: $\int_{-\infty}^{\infty} f(x) dx = 1$
* _pf_ and _pdf_ should be non-negative for all values.

### Cumulative Distribution Function

A cumulative distribution function $F(x)$ is defined as:

$F(x) = Pr( X \le x)$ for $x \in (-\infty, \infty)$

Note that the same definition is applicable for
discrete as well as continuous random variables.
Unlike before, we do not need two different definitions for discrete and continuous.

Properties of $F(x)$:

* $F(x) = 1$ for $x = \infty$
* $F(x) = 0$ for $x = -\infty$
* $F(x)$ is non-decreasing.
* $Pr(X \gt x) = 1 - F(x)$ 
* $Pr(x_1 \lt X \le x_2) = F(x_2) - F(x_1)$
* $F(x) = \sum \limits_{-\infty}^{x} f(x)$ (discrete)
* $F(x) = \int_{-\infty}^{x} f(x) dx$ and $f(x) = d F(x)/ dx$ (continuous)

### Examples

Let us define the probability distribution of a random variable ($X$)
that represents the number of heads on tossing two fair coins.
The random variable is $$X: \{HH, HT, TH, TT\} \rightarrow \{2, 1, 1, 0\}$$

Its probability distribution can be written as:

$Pr(X = 0) = 1/4$  (event: {TT})

$Pr(X = 1) = 1/2$  (event: {HT, TH})

$Pr(X = 2) = 1/4$  (event: {HH})

Point to note is that probability distribution is nothing but a collection of probabilities of the different values taken by the respective random variable.