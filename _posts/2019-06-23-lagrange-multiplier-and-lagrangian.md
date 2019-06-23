---
layout: post
title: Lagrange Multiplier and Lagrangian
---

Lagrange multiplier is a technique to determine a local minima or maxima
of an objective function subject to some constraint.
It allow us to convert the given objective function and the constraint
into a single objective function, which we can use with traditional
techniques, like equating the derivative to zero,
to determine a local minima or maxima.

### Key Idea

Given a function $f(x, y)$, we want to find the value of $(x, y)$ 
that maximizes $f(x, y)$,
subject to the constraint $g(x, y) = 0$.

At the candidate maximum points, the contour lines of
two functions ($f$ and $g$) would graze each other tangentially.
Consequently, the gradients of the two functions would be in the same direction.
We can write the same as:

$\Delta f(x, y) = \lambda \Delta g(x, y)$

$\lambda$ in this equation is called the Lagrange multiplier.

We can solve for $x$, $y$, and $\lambda$, by using the gradient equation together with
the constraint. This would result in the local maxima of the function $f$ subject
to the constraint $g$.

### Lagrangian function

$\mathscr{L}(x, y, \lambda) = f(x, y) - \lambda g(x, y)$

$\mathscr{L}$ is called the Lagrangian function. 
Lagrangian function is an equivalent way to write an objective function with constraint for the purpose of computing the local minima or maxima.

For finding the extrema points (maxima or minima),
one can now compute the partial derivative w.r.t. to $x$, $y$ and $\lambda$ and
equate to zero, and solve for $x$ and $y$.


<!-- ### Example

Maximizing $f(x, y) = x^2y$ under the constraint is $x^2+y^2 = 1$.

Ans: +- sqrt(2/3), +- sqrt(1/3) -->
