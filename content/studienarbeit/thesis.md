---
title: Thesis
date: "2020-09-23"
external_url: https://gepris.dfg.de/gepris/projekt/409474577?language=en
tags:
  - to-do/to-archive
  - -sounding-board
  - -master
  - -sa/processed
  - discussion/2020/2020-10
  - -master/thesis
---

Parent: [Scope of Studienarbeit](Scope of Studienarbeit.md)
See also: [Schönheitsfehler](Schönheitsfehler.md), [Tex stuff](Tex stuff.md), [Spelling](Spelling.md), [Notes on current thesis version](Notes on current thesis version.md), [Fact checks](Fact checks.md)

**\*\*TO BE RESTRUCTURED\*\*** s. [Thesis restructure](Thesis restructure.md)

Introduction

*   [x] Bereits am Anfang (S.1) auf die Navigation eingehen
*   GRK 2543
    *   [x] more on the navigation subtheme (loc. of other tools within camera view of the main probe --
    *   [ ] relate to generalisability of optim.-based methods later on)
*   Problem statement
*   Literature review/Stand der Technik/Other works
    *   Visual tracking review: types of algos available
    *   VI-Review
    *   filt-based, opt-based 
    *   DefSLAM
    *   use of ORB features in def. envs
    *   other papers on SLAM for deformable envs e.g. MIS-SLAM (Chen), Song
    *   [ ] ORB-SLAM3 in lit review
*   Contribution of my Studienarbeit (deformable tracking using vision+IMU)
*   Structure of the thesis, notation etc.

Grundlagen/Theoretical framework

*   The navigation/localisation task
*   SLAM (general)
    *   Subsets of SLAM
    *   [ ] feature-based vs direct SLAM
    *   SLAM rigidity assumption
    *   SLAM front end
        *   Begriffe data association, loop closure etc.
    *   SLAM back end (filtering/optim type)
        *   (adaptability/generalisability to other problems)
        *   MAP estimation stuff; Brief overview filtering-based SLAM (Kalman etc)
*   Sensors in SLAM
    *   Camera
    *   IMU
*   Monocular visual SLAM: problem: depth info
    s.  [Monocular depth perception](Monocular depth perception.md)
    
*   Computer vision
    *   Descriptors: ORB, etc.
        *   Use of ORB for deformable envs.
    *   Bag of words
    *   Camera model (projection equation)

Relevant SLAM algorithms

*   EKF
*   DefSLAM
*   ORB-SLAM?

Overview of the SLAM framework to be implemented
Overall framework: loosely coupled DefSLAM-EKF framework

Test stand setup/Simulation setup
Hardware/software used
Bilddaten generiert in SOFA + fake IMU data

Resuls/Validation + Discussion
Compare DefSLAM algo. with and without IMU

Conclusion
[Ausblick](Ausblick.md)

