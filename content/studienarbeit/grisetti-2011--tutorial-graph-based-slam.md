---
title: Grisetti 2011 - Tutorial graph-based SLAM
date: "2020-10-24"
tags:
  - -resources/-bibliography
  - -resources/-bibliography/bib-to-read
  - -sa/to-be-processed
---

temp

Backlinks: [What is SLAM?](what-is-slam_.md)

Abstract

*   formulate SLAM using a graph
    *   nodes: poses of the robot (as well as landmark postiions) at different points in time
    *   edges: constraints between poses
        *   come from
            *   sensor measurements/observations
            *   robot movement/control input
        *   constraints can contradict each other, due to effect of noise in sensor readings
*   solve the graph, i.e. compute the map: find the spatial configuration of the nodes that best satisfy the constraints/edges
*   tutorial for back-end (optimisation) part of graph-based SLAM

:: Navigation task: requires a map and knowledge of current position relative to locations in the map

The need for an accurate map

*   systems navigating the map don't have to rely on external reference systems like GPS sensors
    *   GPS isn't suitable for indoor environments
*   can operate in complex environments while relying only on their on-board sensors

Filtering vs. smoothing
Filtering: on-line state (robot pose, map) estimation; "on-line" because incremental in nature
Smoothing: full trajectory estimation, typically rely on LSQ minimisation

History of graph-based formulation

*   initially unpopular due to high solving complexity (high dimensional state spaces)
*   later:
    *   use structure of SLAM problem
        *   static world assumption
        *   [Markov assumption](markov-assumption.md)
    *   advancements in sparse linear algebra
*   now: graph-based SLAM is state-of-the-art (w.r.t. accuracy, speed)

Modelling the probabilistic SLAM formulation

*   [DBN](http://www.evernote.com/shard/s484/nl/217355218/9dc7aed8-e237-41d5-90b6-1ed08781529c) (shows temporal structure)
*   Graph-based (shows spatial structure)

Temporal vs spatial pose graphs
![Image.png](./_resources/Grisetti_2011_-_Tutorial_graph-based_SLAM.resources/Image.png)![unknown_filename.png](./_resources/Grisetti_2011_-_Tutorial_graph-based_SLAM.resources/unknown_filename.png)

Graph-based SLAM

*   node:
    *   robot pose, labelled according to location (as opposed to time as in DBN)
    *   measurement acquired at that position
*   edges: spatial constraints (in the form of probability distributions) between poses
    *   from odometry/observations
    *   :: g2o edges are constraints, which are the optim. function terms
    *   edges are like an abstraction of raw measurements into 'virtual measurements' (using probability distributions, observation model etc.)
*   main tasks of graph-based SLAM:
    *   \[graph construction\] constructing the graph from raw measurements
        *   front-end
        *   data association
        *   very sensor-dependent
        *   "How to interpret sensor data to obtain the graph constraints?"
    *   \[graph optimisation\] finding best pose configuration from graph
        *   back-end
        *   relies on abstract representation of data, is sensor agnostic
        *   "How to compute the map given the constraints?"
*   front- and back-end executions are interleaved (front end requires prior term which comes from back-end)

Observation model
![unknown_filename.1.png](./_resources/Grisetti_2011_-_Tutorial_graph-based_SLAM.resources/unknown_filename.1.png)

*   The observation model is usually multimodal:
    *   a single observation may result in multiple edges (in the spatial graph)
    *   "a feature can be observed from multiple view points/camera poses"
    *   the graph connectivity
*   Due to this multimodality, the Gaussian assumption does not hold

