---
layout: post
title: Joint Probability Distribution
---

The notion of probability distribution of a random variable can be extended to
the joint distribution of multiple random variables.
On the same lines, we can define the joint _pdf_, joint cumulative distribution and other various definitions
for multiple random variables.

### Bivariate/Multivariate Distributions

The joint distribution of two random variables $X$ and $Y$ is the collection of probabilities
of the form $Pr((X, Y) \in C)$ for all sets $C$ of pairs of real numbers such that $\{(X, Y) \in C\}$ is an event.

If the values taken by $(X, Y)$ are finite or countable, 
then the distribution is called discrete joint distribution. 
If the values taken by $(X, Y)$ are un-countably infinite, 
then the distribution is called continuous joint distribution.

Similar to the single random variable case, the joint distribution is defined in terms of _pf_ or _pdf_.

* Discrete: $Pr((X,Y) \in C) = \sum \limits_{(x, y) \in C} f(x, y)$
* Continuous: $Pr((X, Y) \in C = \int_C \int f(x, y) dx dy$

A joint distribution is called bivariate if the number of random variables
involved is two and multivariate for more than two.

Another way to interpret joint distribution for *discrete* random variables
$X$ and $Y$ is a table whose number of entries is the product of the number of entries in the distribution of $X$ and $Y$.
In the vertical direction, random variable $X$ takes different values, and
in the horizontal direction, random variable $Y$ takes different values.
For every combination of $X$ and $Y$, the table lists the probability of the event $X=x \land Y=y$.

### Cumulative distributions

Cumulative distribution function for joint distribution is defined as:

$F(x, y) = Pr(X \le x\ and\ Y \le y)$

### Marginal Distribution
Given a joint distribution we can find the distribution of a single random
variable from it. The distribution of a random variable computed from a
joint distribution is called marginal distribution.
Consequently, we can define marginal _pf_/_pdf_ as well as marginal _cdf_.

The term marginal comes from the fact that these probabilities occur at the margins of the table in case of discrete joint distributions.

#### Marginal _pf_/_pdf_

$f_X(x) = \int_{-\infty}^{\infty} f(x, y) dy$, similarly for Y.

$f_X(x) = \sum \limits_{y \in domain(Y)} f(x, y)$

Note the marginal _pf_/_pdf_ is a valid probability distribution, hence,
all the rules of [probability distribution]() apply to it.

#### Marginal _cdf_
$F_X(x) = lim_{y \rightarrow \infty} F(x, y)$ similarly for Y.

### Independence of random variables

Two random variable $X$ and $Y$ and independent if for every events $A$
and $B$ the following holds:

$$
Pr(X \in A \land Y \in B) = Pr(X \in A) Pr(Y \in B)
$$

### Conditional distributions

Conditional distribution is a generalization of conditional probability.
Conditional distribution represents collection of probabilities when
an event of one random variable is conditional of an event of
the other random variable.

Probability of event $x$ of $X$ conditioned on event $y$ of $Y$ is written as:

$Pr(X = x | Y = y) = Pr(X = x \land Y = y)/ Pr(Y = y) = f(x, y)/f_Y(y)$

Here $f(x, y)$ is the joint _pf_/_pdf_ and $f_Y(y)$ is the marginal _pf_/_pdf_ of $Y$.

The equation is commonly written as follows ($\land$ is replaced by comma, and events have been omitted).

$$Pr(X | Y) = Pr(X, Y)/ Pr(Y)$$  
equivalent to
$$Pr(X, Y) = Pr(X | Y) Pr(Y)$$

This is also called the chain rule of probability for random variables. For three random variables, it is written as:

$$Pr(X_1, X_2, X_3) = Pr(X_1 | X_2, X_3) Pr(X_2, X_3)$$

#### Conditional distribution

Conditional distribution of random variable $Y$ conditioned on random 
variable $Y$, $g_X(x/y)$ can be computed as:

$g_X(x/y) = f(x, y)/f_Y(y)$

For every $y$, $g_X(x/y)$ is a probability function (_pf_/_pdf_) as a function of $x$.

Note: a conditional distribution is a mere collection of conditional probabilities. It is a valid probability distribution and all the rules of
probability apply to it.
