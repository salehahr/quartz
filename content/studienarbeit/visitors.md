---
title: Visitors
date: "2020-07-15"
tags:
  - software/SOFA/data-types
  - -sa/processed
---

Source: [SOFA extended documentation](SOFA extended documentation.md)
Parent: [Data structure in SOFA](Data structure in SOFA.md)
Backlinks: [Scene graph in SOFA](Scene graph in SOFA.md), [Simulation algorithms in SOFA](Simulation algorithms in SOFA.md)

*   For processing of data structure: parent to child
*   Allows decoupling of physical model from simulation algo
    e.g. Easy to replace a time integrator, which wouldn't be the case in a dataflow graph (coupling of data and algo)
    
*   Nodes with multiple parents are traversed only once (pruning of top-down traversals)

