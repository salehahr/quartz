---
title: Event
date: 2022-05-12
tags:
  - math/probability-theory
  - -definitions
---

**Parent**: [probability-theory](math/statistics/probability-theory.md)  
**See also**: [random-variable](studienarbeit/random-variable.md)

# Event $E$

**Source**: [Wiki](https://en.wikipedia.org/wiki/Experiment_(probability_theory)) 

$$E = \left\{ \omega_i \right\} \subseteq \Omega$$
* Group of [outcomes](definitions/outcome.md)
* Every event $E$ is assigned a probability of it happening
* Example event: $E = \left\{ \omega \in \Omega \mid X(\omega) \leq x \right\}$  
  "Set of all [outcomes](definitions/outcome.md) $\omega$ which satisfy the condition $X(\omega) \leq x$"
    $$P(E) = P(X \leq x) = p_E$$


## Example
Experiment: flip a coin twice
$$\Omega = \left\{ (H, H), (H, T), (T, H), (T, T) \right\}$$

Event $E_1$: $H$ occurs in either flip
$$E_1 = \left\lbrace (H, H), (H, T), (T, H) \right\rbrace \subset \Omega$$

Event $E_2$: same result twice
$$E_2 = \left\{ (H, H), (T, T) \right\} \subset \Omega$$


## Relationships between events
**Source**: [blitzstein-hwang](bibliography/blitzstein-hwang.md)

| Notation                                                          | Description             |
| ----------------------------------------------------------------- | ----------------------- |
| $A \subseteq B$                                                   | $A$ implies $B$         |
| $A~\cap~B=\emptyset$                                              | mutually exclusive      |
| $\bigcup_i^n A_i = \Omega,~A_i~\cap~A_j=\emptyset$ for $i \neq j$ | partitions of $\Omega$  |
| $(A~\cap~B^c) \cup (A^c~\cap~B)$                                  | $A$ or $B$ but not both |
