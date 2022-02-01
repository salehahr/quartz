---
title: DefSLAM framework
date: "2020-11-20"
tags:
  - -sa/processed
  - SLAM/algos/DefSLAM
  - -published
---

**Source**: [Lamarca 2020 DefSLAM](lamarca-2020.md)  
**See also**: [template-substitution-in-defslam](studienarbeit/template-substitution-in-defslam.md)

"Fusion of the methods available for processing non-rigid monocular scenes"

1.  Deformation tracking \[front end\]
    *   estimates/recovers/optimises:
        *   camera pose
        *   scene deformation / deformation of map points (observations)
    *   the map points are then embedded into the template Tk (to compute their position on the surface)
    *   operates at frame rate
    *   SFT-based ([shape from template](studienarbeit/sft.md)), requires prior geometry (template of scene at rest) for the currently being viewed map
    *   Map points are deformed (updated) by solving an optimisation problem
        min { reprojection error + deformation energy } per frame
        
2.  [Deformation mapping](studienarbeit/mapping-step-by-step-in-defslam.md) \[back end\]
    *   periodically re-estimate template to adapt it to current observation (deformed map points from tracking)
    *   extends the map as it provides the updated geometry for when new regions are visited
    *   operates at keyframe rate
    *   based on NRSfM ([non-rigid structure from motion](studienarbeit/nrsfm.md)), s. also [NRSfM in DefSLAM](studienarbeit/nrsfm-in-defslam.md)
    *   recovers a surface for the last keyframe, by processing the map points of several keyframes from the same scene region
    *   from the surface, a deformed map is generated and passed to the tracking thread

![Image.png](./_resources/DefSLAM_framework.resources/Image.png)
