---
title: conditional-probability
date: 2022-05-12
tags:
  - math/probability-theory
  - -definitions
---

**Parent**: [probability-theory](math/statistics/probability-theory.md)  

# Conditional probability

**Source**: [blitzstein-hwang](bibliography/blitzstein-hwang.md) 

$$P(A|B) = \dfrac{P(A~\cap~B)}{P(B)}$$

| Notation       | Description                |
| -------------- | -------------------------- |
| $P(A)$         | prior held belief          |
| $B$            | evidence that is observed  |
| $P(A\lvert B)$ | posterior (updated belief) |


## Properties
1. $0 \leq P(A|B) \leq 1$
2. $P(\Omega|E) = 1$, $P(\emptyset | E) = 0$
3. For disjoint events $A_i$, $P(\bigcup_i A_i | E) = \sum_i P(A_i|E)$
4. Complement: $P(A^c | E) = 1 - P(A|E)$
5. Union: $P(A\cup B|E) = P(A|E) + P(B|E) - P(A\cap B|E)$