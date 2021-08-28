---
title: SOFA extended documentation
date: "2020-07-15"
tags:
  - software/SOFA
  - -resources/-bibliography
  - -resources/-bibliography/bib-read
  - -sa/processed
---

Source: <http://hal.inria.fr/hal-00681539>
Authors: Faure et al
Backlinks: [Scope of Studienarbeit](scope-of-studienarbeit.md)

Abstract

*   SOFA: open source C++ library
*   mainly for interactive physical/medical simulation
*   modular approach by decomposing simulators into its constituent components (DOF, differential equations, solvers etc), and organising them in a scenegraph data structure
*   multimodel representation of objects (collision model, visual model etc)

Chapters

Read

*   1: [introduction](introduction.md)
*   2: [multimodel framework](http://www.evernote.com/shard/s484/nl/217355218/61adbad2-ef29-4eb6-8b79-bc7e2065df24?title=Models%20in%20SOFA)
*   3: [data structures](http://www.evernote.com/shard/s484/nl/217355218/2f8350ca-46bc-4a46-aa5d-d40d64881a65?title=Data%20structure%20in%20SOFA)
    *   3.1 [scenegraph](http://www.evernote.com/shard/s484/nl/217355218/bf18694a-5cea-4dbe-8ba2-95b6c187a636) and [visitors](http://www.evernote.com/shard/s484/nl/217355218/8e1b1539-2194-4c70-b3b5-c3d4328fa151)
    *   3.2 data and engines
    *   3.3 [mesh geometry](mesh-geometry.md) and [mesh-topology](mesh-topology.md)
*   4: [simulation algorithms in SOFA](simulation-algorithms-in-sofa.md)
    *   ODE integration ([ODE solvers](ode-solvers.md))
    *   Linear equation solution ([linear solvers](linear-solvers.md))
    *   Complex constraints ([constraint solvers](constraint-solvers.md))
    *   [Collision detection and response](collision-detection-and-response.md)
    *   GPU support

Skimmed

*   5: user interface
    *   5.3: [haptic rendering](http://www.evernote.com/shard/s484/nl/217355218/79a1235b-03d4-4fbe-a1a6-ad4bedc46d92)

Later

*   7: conclusion
*   6: examples

