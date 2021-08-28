---
title: Dynamic Bayesian Network formulation of SLAM
date: "2020-10-24"
tags:
  - to-do/missing-tag
  - -sa/processed
---

Source: [Grisetti 2011 - Tutorial graph-based SLAM](grisetti-2011---tutorial-graph-based-slam.md)

Dynamic Bayesian Network

![unknown_filename.png](./_resources/Dynamic_Bayesian_Network_formulation_of_SLAM.resources/unknown_filename.png)
Solution of full SLAM problem:  ![unknown_filename.1.png](./_resources/Dynamic_Bayesian_Network_formulation_of_SLAM.resources/unknown_filename.1.png)
Transition model: ![unknown_filename.3.png](./_resources/Dynamic_Bayesian_Network_formulation_of_SLAM.resources/unknown_filename.3.png)
Observation model: ![unknown_filename.2.png](./_resources/Dynamic_Bayesian_Network_formulation_of_SLAM.resources/unknown_filename.2.png)

*   The observation model is usually multimodal: a single observation may result in multiple edges (in the spatial graph)
*   Therefore, the Gaussian assumption does not hold

