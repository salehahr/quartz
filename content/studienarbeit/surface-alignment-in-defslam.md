---
title: Surface alignment in DefSLAM
date: "2020-11-25"
tags:
  - -sa/processed
  - to-do/missing-link
  - SLAM/algos/DefSLAM
---

Parent: [Mapping step-by-step in DefSLAM](mapping-step-by-step-in-defslam.md)
Source: [Lamarca 2019 DefSLAM](lamarca-2019-defslam.md)

Goal:

*   to scale the up-to-scale surface (output of NRSfM) to the proper dimensions
*   get an idea of the proper dimensions from the already estimated map
    *   i.e. resulting surface must match the scale of the template T\_(k-1)
    *   T\_(k-1): deformed map generated by the tracker at the instance of KF=k insertion, with shape-at-rest of S\_(k-1) generated from KF:(k-1)
*   result: scale-corrected shape-at-rest Sk

Method:

*   alignment of the map points using Sim(3)
*   Sim(3): basically a transformation that enlarges/shrinks by a certain scale (as far as I understand it). For more info see \[[Wiki](http://en.wikipedia.org/wiki/Similarity_%28geometry%29
- In_Euclidean_space)\].
    ![unknown_filename.png](./_resources/Surface_alignment_in_DefSLAM.resources/unknown_filename.png) scale \\hat{S} to S
    
*   Minimise the error between transformation of map points in \\hat{S} and the map points in S
    ![unknown_filename.1.png](./_resources/Surface_alignment_in_DefSLAM.resources/unknown_filename.1.png)
    where the arguments are the transformation parameters
    

Generating of the new template Tk from Sk

*   Use Delaunay triangulation to make a triangular mesh from Sk
*   New map point poses are computed
    *   from the camera observation
    *   by constraining them to be on the surface Sk (embedding of the re-observed map points)
