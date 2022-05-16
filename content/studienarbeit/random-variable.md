---
title: Random variable
date: 2020-08-31
tags:
  - -definitions
  - -sa/processed
  - math/statistics
  - math/probability-theory
---

# Random variable $X$

**Source**: [Wiki](https://en.wikipedia.org/wiki/Experiment_(probability_theory))
* *Alternative name*: stochastic variable
* Function that assigns each elementary outcome $\omega$ in the sample set $\Omega$ to another set $\mathcal{A}$ (often to $\mathbb{R}$)
    $$X: \Omega \rightarrow \mathcal{A}$$
* $P(X = x)$ is the probability that the function $X$ attains the value $x \in \mathcal{A}$
* $x$: specific realisation of a random variable $X$
* Can be discrete (e.g. number of students) or continuous (e.g. height of students)

## Example
[Source](https://www.reddit.com/r/learnmath/comments/4ti8nm/what_is_the_difference_between_x_and_x_in_regards/d5jrayi/)
* Experiment: two dice are thrown
* Sample set: $\left\{ (D_i, D_j)  \right\}$ $\forall\, i,j$
* $X$: random variable that gives the number of dice with sixes
* Example trials:
    * Trial 1: (2, 3) --> $X = 0$
    * Trial 2: (6, 1) --> $X = 1$
    * Trial 3: (6, 6) --> $X = 2$