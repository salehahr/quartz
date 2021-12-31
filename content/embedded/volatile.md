---
title: volatile
date: 2021-12-31
tags:
  - programming/c
---

**Source**: [samek-embedded](bibliography/samek-embedded.md)

* The `volatile` keyword indicates that the variable might change spontaneously.
* For example: variables which depend on user input and are not affected by program instructions
* It can be useful to define a variable to be volatile when high levels of optimisations are performed by the compiler, e.g. for counter variables which are not used outside of loops.