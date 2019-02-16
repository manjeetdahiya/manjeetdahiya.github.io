---
layout: post
title: Conditional Probability and Independent Events
---

### Conditional probability

Given two events $A$ and $B$, the probability of occurrence of event $A$ after learning the occurrence 
of event $B$ is called *conditional probability* of $A$ conditioned on the event $B$.
It is denoted as $Pr(A\|B)$ and defined as follows:

$$
Pr(A|B) = Pr(A \cap B)/ Pr(B)
$$

Note that $Pr(A\|B)$ is undefined if $Pr(B) = 0$.
Also note that $Pr(A\|B)$ is *just a definition*; it is simply a term that is equal to $Pr(A \cap B)/ Pr(B)$.

Consider an example of rolling of an unbiased dice.
If we want to know the probability of occurrence of 2
given that an even number has been rolled, then we are asking the conditional probability of 
number 2 conditioned on the event that an even number has been rolled.
To complete the example, $$B = \{2, 4, 6\}$$ (event that an even number is rolled)
and $$A = \{2\}$$ (event that 2 is rolled) and we want to know $Pr(A\|B)$.
Event $$A \cap B =\{2\}$$, therefore, we can compute:
$Pr(A \cap B) = 1/6$, $Pr(B) = 3/6$, and finally, $Pr(A\|B) = 1/3$.

Alternatively, conditional probability can be thought of as the probability
of occurrence of event $A$ considering the sample space as event $B$.
Note that the sample space usually gets reduced, except the case when event $B$ is the sample space.
Following equation denotes the same, assuming that the outcomes are equi-probable.

$$
Pr(A|B) = |A \cap B|/|B|
$$

$\|A \cap B\|$ represents the number of outcomes where $A$ and $B$ both occur, 
and $\|B\|$ is the number of outcomes where $B$ occurs. 
The dice example example can also be computed using this formula, as the outcomes are
equi-probable.

### Chain rule
Massaging the definition of conditional probability results in the so called
the chain rule of probability.

$$
Pr(A|B) Pr(B) = Pr(A \cap B) = Pr(B|A) Pr(A)
$$

Given $Pr(A) \not = 0$ and $Pr(B) \not = 0$.

### Law of total probability
Suppose events $B_1, ..., B_k$ form a partition of the sample space $S$, 
then for every event $A$ in the sample space $S$:

$$
Pr(A) = \sum\limits_{i = 1}^k Pr(A|B_i) Pr(B_i)
$$

### Independent events
Conditional probability leads us to the notion of independence.
Two events $A$ and $B$ are said to be independent if the occurrence of
one does not influence the probability of occurrence of the other, and vice versa.
In other words, if the conditional probability of $A$ conditioned on
$B$ is same as probability of $A$, and the other way too, then these two events 
are independent. Formally, $A$ and $B$ are independent iff:

$$
Pr(A|B) = Pr(A)
$$

However, defining independence using conditional probability has issues, 
as the $Pr(A \| B)$ in itself is undefined when $Pr(B) = 0$.
To cover all the cases following is a better definition of
independent events:

$$Pr(A \cap B) = Pr(A) Pr(B)$$

Note that for $Pr(A) \not = 0$ and $Pr(B) \not = 0$ both the definition are equivalent.
