---
title: Data association in DefSLAM
date: "2020-11-20"
tags:
  - to-do/go-through-literature-later
  - localisation/data-association
  - -sa/processed
  - SLAM/algos/DefSLAM
---

**Source**: [Lamarca 2020 DefSLAM](lamarca-2020.md)
**See also**: [Data association](SLAM/data-association.md)

*   Goal: match keypoints in current frame (newly extracted) with map points (already in map/system)
*   Use the active matching strategy proposed in \[Agudo 2015\]: “Simultaneous pose and non-rigid shape with particle dynamics,”

**Steps** 

1.  ORB points (keypoints) are detected in current frame
2.  Camera pose Tcw is predicted
    *   using camera motion model
    *   camera motion model: function of past camera poses
3.  Predict where map points (existing in map) would be imaged, based on last estimated template
    i.e. now we know the camera movement, project (predict) the previous points to the next frame
    
4.  Define a region around each predicted point
    *   One/some/no keypoints would now lie within these regions
    *   Search the region around the predicted points for keypoints to be matched with the projected map point
5.  Predicted point gets matched to one of the keypoints
    *   the one with the most similar ORB descriptor
    *   Hamming distance as similarity criterion (between ORB descriptors)

