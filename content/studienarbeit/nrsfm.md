---
title: Non-rigid Surface from Motion
date: "2020-11-20"
tags:
  - to-do/go-through-literature-later
  - SLAM/deformable-SLAM
  - to-do/not-good-enough
  - -sa/to-be-processed
  - -published
---

**Notes**:
* Original NRSFM paper?  
	https://www.cs.dartmouth.edu/~lorenzo/Papers/TorrHertzBreg-pami08.pdf
* A Phd thesis [Kumar] https://openresearch-repository.anu.edu.au/handle/1885/164278?mode=full


---

**Source**: Kumar
* The problem with dynamic or non-rigid scenes:  
	if we project a scene point into a camera image plane, there will be several possible 3D configurations!
* Allowing arbitrary deformations makes the 3D reconstruction an ill posed problem (underconstrained) --> need to make additional assumptions about the object or scene (make more constraints)!



---


**Source**: [lamarca-2020](studienarbeit/lamarca-2020.md)
**See also**: [nrsfm-in-defslam](studienarbeit/nrsfm-in-defslam.md), [sfm](studienarbeit/sfm.md)

## NRSfM (non-rigid structure from motion)

*   batch processing of images to recover deformation
*   computationally demanding — slower than [SfT](studienarbeit/sft.md)

### Orthographic NRSfM

*   usually fails with very large deformations
*   uses an orthographic camera projection/model
*   (weak approximation to the perspective camera) — a limitation, as many vision-related applications have a significant perspective effect
*   exploits
    *   spatial constraints
    *   temporal constraints
    *   spatiotemporal constraints
*   usually ok for small deformations, but not for very large deformations

### Perspective NRSfM

*   the perspective camera model is more accurate than the orthographic one
*   also uses the isometry assumption (as in SfT methods), which has produced good results in NRSfM
*   Parashar 2018 "Isometric NRSfM" \[6\] local method that handles occlusions and missing data well