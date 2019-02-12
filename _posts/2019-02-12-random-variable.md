---
layout: post
title: Random Variable
---
A random variable is an abstraction that assigns measurable numerical quantities to 
the outcomes of a stochastic phenomenon.
A random variable is a *function* that *maps* the sample space 
(of the experiment, i.e., the stochastic phenomenon) to some numerical quantities.
In other words, a random variable of an experiment is a *function* with its domain as the sample space 
and real numbers as its range.

For example, in an experiment of tossing two coins, a random variable ($X$) 
representing the number of heads is an example of a random variable. 
Formally, $X$ is a function from its sample space to integers. 
Following is the mathematical formulation of $X$:

$$X: \{HH, HT, TH, TT\} \rightarrow \{2, 1, 1, 0\}$$

We may have a different random variable for the same experiment, e.g., the following
mapping gives us a two bit number assuming head and tail to be 0 and 1 respectively.

$$X_{2bit}: \{HH, HT, TH, TT\} \rightarrow \{0, 1, 2, 3\}$$

In the same experiment, we can have two random variables ($X_1$ and $X_2$) for
the two coins. Where $X_i$ (for i in 1, 2) maps head to 1 and tail to 0.

$$X_i: \{H, T\} \rightarrow \{1, 0\}$$

The examples demonstrate that choosing a random variable is dependent on how one
wants to model the experiment. It is simply dependent on the problem at hand.

Note that we may have operations on compatible random variables.
For our example, we can write:

$$X = X_1 + X_2$$

### Continuous and discrete random variable

A random variable that takes finite number of values is called 
a discrete random variable. $X_{2bit}$ is a discrete random variable, 
its range takes four distinct values.

A random variable that takes un-countably infinite values is called 
a continuous random variable. Modeling of noise in the current measurement 
of an electric circuit as a random variable is an example of continuous 
random variable, although here the sample space in itself is a measurable quantity.
Another example is height of a person selected at random in Gurgaon.
The range in both these cases could take un-countably infinite values, thus,
continuous random variables.

### Just an abstraction!

Note that random variable is just an abstraction. It allows Mathematicians to forget about
the underlying stochastic phenomenon, and enable them to build higher order theories
on top of it.
For example, a number of different stochastic phenomena may take the same probability distribution, and
the abstraction of random variable allows us to consider them one.
