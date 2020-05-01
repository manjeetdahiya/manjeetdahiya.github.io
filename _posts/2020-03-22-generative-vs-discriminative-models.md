---
layout: post
title: Generative vs Discriminative Models
---

Given a setup with $X$ and $Y$ as input and output variable respectively.
The modeling to predict $Y$ from $X$ can be done in multiple ways.
Following are a few common ones:

### Generative Model

* We learn the probability model $P(X \| Y)$ and use Bayes' theorem to predict
$P(Y \| X) \propto P(X \| Y) P(Y)$.
* It is a comprehensive modeling of the distribution of $X$ for every $Y$. 
  It requires significantly high amount of data in comparison with discriminative 
  modeling to achieve good predictive capability.
* We can sample using the distribution and generate synthetic $X$ for a given $Y$.
* Examples: ngram or neural language modeling and Naive Bayes models

### Discriminative Model

* We directly learn $P(Y \| X)$ and use it at the time of prediction.
* We are learning a model to just disambiguate the classes (i.e., $Y$) and not the
  representation of the classes.
* In contrast with generative models, discriminative models are less demanding in terms of
  training data.
* Examples: logistic regression, SVMs and tree based models
