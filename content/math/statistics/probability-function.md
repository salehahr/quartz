---
title: probability-function
date: 2022-05-12
tags:
  - math/probability-theory
  - -definitions
---

**Parent**: [probability-theory](math/statistics/probability-theory.md)  

# Probability function
        
**Source**: [blitzstein-hwang](bibliography/blitzstein-hwang.md) 

Maps an event $E$ to probability values.

The probability function $P$ must satisfy the axioms:
1. $P(\emptyset)=0$, $P(\Omega)=1$
2. $P\left(\, \bigcup_i A_i \,\right) = \sum_i P(A_i)$
    if the events $A_i$ are mutually exclusive.
    
## Properties
1. $P(A^c) = 1 - P(A)$
2. If $A \subseteq B$, then $P(A) \leq P(B)$
3. $P(A~\cup~B) = P(A) + P(B) - P(A~\cap~B)$