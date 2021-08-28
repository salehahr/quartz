---
title: Haptic rendering
date: "2020-07-15"
tags:
  - software/SOFA
  - misc/haptic-feedback
  - -sa/processed
---

Source: [SOFA extended documentation](sofa-extended-documentation.md)

The main interest of interactive simulation is that

*   the user can modify the course of the computations in real-time
*   when a virtual medical instrument comes into contact with some models of a soft-tissue, instantaneous deformations must be computed
    *   This visual feedback of the contact can be enhanced by haptic rendering so that the surgeon can really feel the contact."

Two main issues in SOFA for providing haptics

1.  Haptic forces need to be computed at 1 kHz
    However: real-time visual feedback (w/o haptic) is obtained at 30 Hz
    
2.  Haptic feedback could artificially add some energy inside the simulation
    1.  may create instabilities if the control is not passive

Thus
Two different approaches:

1.  Virtual Coupling
2.  Constraint-based rendering
    COMMENT: possibly what I need  
    

... (skimmed)

