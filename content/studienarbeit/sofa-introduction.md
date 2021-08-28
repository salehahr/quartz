---
title: SOFA Introduction
date: "2020-07-15"
tags:
  - software/SOFA
  - -sa/processed
---

Source:  [SOFA extended documentation](sofa-extended-documentation.md)

Goal of SOFA: To provide a highly modular framework for interactive medical simulation, enabling collaboration across different disciplines
Concept: [scene-graph](scene-graph.md)\-based multimodel representatios

How it works:

*   Simulators are broken down into independent components
    *   Component: an aspect of the simulation
    *   e.g. DOF, forces, constraints, ODEs/PDEs, solvers, algorithms
*   Components are organised in a [scene graph](scene-graph.md) data structure
*   Simulated objects represented via several [models](models.md)

