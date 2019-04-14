---
layout: post
title: Quantile-Quantile Plot (Q-Q plot)
---

A Quantile-Quantile (Q-Q) plot is a graphical technique to check if a sample follows a particular distribution.
It can also be used to check if two different samples follow the same distribution.
It is a scatter plot between the quantiles of the two distributions that need to be compared.
A Q-Q plot approximately results in the straight line $y = x$ if the two distributions are identical.

This post presents the definition of quantile and quantile function, and
it finally describes the Q-Q plot.

#### Quantile

There are at least two different definitions of quantile. This post presents two of them, denoted as
$q$-quantile and $p$-quantile.

The $q$-quantiles of a *sorted* sample ($S$) are $q-1$ cut points, of the same type as the sample data,
that divide the sample into $q$ equally sized partitions.
For example, 2-quantile, also called median, divides a sorted sample into two equal parts.
4-quantiles, also called quartiles, divide a sorted sample into four equal parts.
Similarly, 100-quantiles, also called percentile, divide into hundred equal parts.

<!-- Let us take a concrete example. We have a sorted sample {2, 4, 5, 10, 12, 14, 15, 17, 80, 100} -->

A $p$-quantile of a *sorted* sample ($S$) is a cut point ($s$), of the same type as the sample data, such that
$s$ is greater than equal to $p$ proportion of the sample.
$p$-quantile is a generalization of $q$-quantile. The $q$-quantile can be computed from $p$-quantile
using the following equation:

$$
\texttt{q-quantile} = \{\texttt{p-quantile}(k/q) \mid k \in \mathbb{Z} \land k \in [1, (q-1)]  \}
$$

Note that both these definitions are applicable to a probability distribution also.
$q$-quantiles divide the probability distribution into $q$ contiguous ranges each having $1/q$
probability. Similarly, $p$-quantile divides the probability distribution such that
$Pr(X \le  \texttt{p-quantile}(p)) = p$.

#### Quantile function

Given a random variable $X$,
the function $\texttt{p-quantile} : p \rightarrow X$ for $p \in [0, 1]$ is called a quantile function.
It takes a $p$ and returns the minimum value of $x$ such that
$Pr(X \le x) = p$. Note that $Pr(X \le x)$ is the cumulative distribution function ($F(x)$) of $Pr$, thus,
we can write the same equation as $F(x) = p$, and also as, $x = F^{-1}(p)$.
Where function $F^{-1}$ is the inverse function of the function $F$.
In other words, quantile function (i.e., $p$-quantile) is the inverse of cumulative distribution function $F(x)$.

#### Quantile-Quantile plot

A Q-Q plot for two distributions/samples is a plot of the quantiles of the two distributions/samples.
Formally,
for a distributions/samples $A$ and $B$,
Q-Q plot is a scatter plot of $n$ points ($n \in \mathbb{Z^+}$)
where the points are
$(\texttt{q-quantile}_A(i/n), \texttt{q-quantile}_B(i/n))$ for $i \in [0, n) \land i \in \mathbb{Z}$.

The idea is that if the distributions are identical, then the quantiles should
be approximately equal. For example, in case of quartiles,
the first quartile should
be roughly same for both the distributions, and similarly, the other quartiles.
Thus, resulting in the straight line $y = x$.