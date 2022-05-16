---
title: bayes-rule
date: 2022-05-12
tags:
  - math/probability-theory
  - -definitions
---

**Parent**: [probability-theory](math/statistics/probability-theory.md)  

# Bayes rule

**Source**: [blitzstein-hwang](bibliography/blitzstein-hwang.md) 

$$P(A|B) = \dfrac{P(B|A) P(A)}{P(B)}$$

## Extra conditioning
"Everything is conditioned on $C$."

$$P(A|B, C) = \dfrac{P(B|A, C) P(A|C)}{P(B | C)}$$
given $P(A\cap E) > 0$ and $P(B\cap E) > 0$.

Alternative approaches for interpretation
1. $B, ~C$ as a single event $B\cap C$  
        $$P(A|B,C) = \dfrac{P(A, B, C)}{P(B, C)}$$
2. Swap roles of $B$ and $C$
    $$P(A|B, C) = \dfrac{P(C|A, B) P(A|B)}{P(C | B)}$$