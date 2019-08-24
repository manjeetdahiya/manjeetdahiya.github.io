---
layout: post
title: Parametric vs Non-parametric Models
---

One of the criteria to classify machine learning or statistical learning 
approaches is parametric vs non-parametric models.
This post presents the contrast between the two.

A machine learning model is simply a mathematical function $Y = f(X)$ between the input (X) and the output ($Y$). The goal of different machine learning approaches is to learn this function given
some observed input and output data.

A parametric approach assumes the functional form (i.e., shape) of the mathematical function ($f$) by construction. That is, it assumes that the function belongs to a particular family of mathematical functions, e.g., linear, quadratic etc. 
The goal is now to determine the coefficients (parameters) of the different components of the function basis the training data.
Linear regression is an example of such an approach. It is *assumed* that the input and output follow the relation $Y = \beta_0 + \beta_1 X$ and the goal is to determine the values of the parameters, i.e.,  the coefficients $\beta_0$ and $\beta_1$. Note that the function
belongs to the family of straight lines and different values of the parameters will form different straight lines.

A non-parametric approach on the other hand does not make any assumptions about the functional form, it is very flexible and can take any shape.
It could be a very complex function, combination of extremely large number of non-linear functions or it could be a rule like large margin boundary or it could be be a simple estimation of density or discriminant outcome in the desired input space.
k-nearest neighbor and decision trees are non-parametric approaches
and there are no inherent assumptions about the functional forms.


The following points present a contrast between the two approaches:

* Unlike non-parametric models, parametric models make strong assumptions about the relation between the input and output.
* Parametric models behave poorly if the assumptions are not met.
* Usually, less data is required for parametric models vs huge data requirements for non-parametric models.
* Risk of overfitting in non-parametric models -- one has to tune the complexity for better results.
* Given the functional form, parametric models are good at interpretability, specifically, inference, which is not possible in non-parametric models. Some of the simpler non-parametric like decision trees might be interpretable, however, without the possibility of inference.
* Parameters of parametric approach selects the concrete function within the family of functions. In non-parametric model, the final function could be anything.
* When it is given that the model follows the chosen shape, it is always wise to chose the parametric approach for various reasons.
* Non-parametric models tend to fail with higher dimensions due to the *curse of dimensionality*. It is not the case with parametric models as long as the assumption about the choice of function is met.
* Examples of parametric models: linear regression, logistic regression. conditional random fields, naive bayes classifier, LDA, perceptron. Examples of non-parametric models: k-nn, decision trees, SVM, smoothing splines, deep neural networks, infinite mixture model.
