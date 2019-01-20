---
layout: post
title: The Axiomatic Definition of Probability
---

In contrast with the post on [probability interpretations]({{ site.baseurl }}{% post_url 2018-12-11-probability-interpretations %}),
this post presents the mathematical definition of probability.
The calculus of probability is built on three axioms, also called the Kolmogorov axioms.
Related terminology is presented first, followed by the axioms and the definition.

### Terminology: Experiments, Sample space, Outcomes and Events

An experiment under study is a process, real or hypothetical, with one or more *outcomes*, i.e., observable results.
All possible outcomes of the process are known in advance and is called the *sample space* of the experiment.
An *event* is a well-defined set of the possible outcomes of an experiment.
Clearly, an event is a subset of the sample space. For example:

**Experiment**: Rolling a dice

**Outcomes:** 1, 2, 3, 4, 5, and 6 are the outcomes of the process.

**Sample space**: $S = \{1,2,3,4,5,6\}$

**Events:**
* Even number is obtained: $A = \{2,4,6\}$
* The number 1 is obtained: $B = \{1\}$
* Negative number is obtained: $C = \{\}$, usually denoted as $\phi$. Empty set is also an event.
* Sample space ($S$) in itself is also an event.

### The axiomatic/mathematical definition of probability
Our goal is to assign a probability value to the different events of an experiment.
The probability of event A is represented as $Pr(A)$. 
We first start with stating the three axioms of the framework of probability 
and finally define the term probability.

**Axiom 1:** For every event $A$, $Pr(A) \ge 0$ 

**Axiom 2:** Probability of the event that the sample space occurs is one: $Pr(S) = 1$

**Axiom 3:** For disjoint events $A_i$, $Pr(\cup A_i) = \Sigma Pr(A_i)$

**Definition** Probability: A probability measure, or simply a probability, is a specification of $Pr(A)$ 
for all events $A$ that satisfy the three axioms of probability.

#### Theorems that can be derived from the axioms
* $Pr(\phi) = 0$
* $Pr(A^c) = 1 - Pr(A)$
* $0 \le Pr(A) \le 1$
* $A \subset B \Rightarrow Pr(A) \le Pr(B)$
* $Pr(A \cup B) = Pr(A) + Pr(B) - Pr(A \cap B)$

### Calculating probability
The probability of an event of an experiment can be computed by using the axioms 
and certain properties of the outcomes.
For example, an experiment is said to have a *simple sample space* 
if the probability of every outcome is equal. 

A sample space with $n$ outcomes is called a simple sample space if the probability 
of each outcome is the same.
Since every outcome is distinct (disjoint events) and 
the total probability of the union of all outcomes is 1, 
the probability of each outcome is $1/n$ (using Axiom 2 and Axiom 3).

By using Axiom 3, the probability of the event containing $m$ outcomes can be proved to be 
equal to $m/n$. More formally, the probability of an event $A$ for simple sample spaces is written as:

$$Pr(A) = |A|/|S|$$

Once the formula to compute the probability of simple sample spaces is defined,
it is straight forward to compute the probability of different events.
Depending upon the problem at hand, suitable counting rules like permutations,
combinations, multiplication rule etc. can be used to compute the values of 
$$|A|$$ and $$|S|$$, and finally, the probability measure.