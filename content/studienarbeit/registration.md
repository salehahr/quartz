---
title: Registration
date: "2020-07-23"
external_url: https://www.sofa-framework.org/applications/marketplace/registration/
tags:
  - software/SOFA/plugins
  - -definitions
  - -sa/processed
  - registration
  - -published
---

* Aligning two points, each in different spaces respectively, together

## Examples
* aligning an endoscope coordinate frame to CT data (based on a similarity metric between endoscopic image and CT image) -- from https://pubmed.ncbi.nlm.nih.gov/25991876/
* match virtual surface to corresponding endoscopic video -- https://ieeexplore.ieee.org/document/958638


---

**Parent**: [SofaPython Index](studienarbeit/sofapython-index.md)

*   allows a matching between deformable surfaces
*   finds spatial transformations to align two point sets or two meshes
*   done based on:
	*   either target surfaces (ClosestPointRegistrationForceField , RegistrationContactForceField)
	*   or target images (IntensityProfileRegistrationForceField), which requires the use of the [image plugin](https://www.sofa-framework.org/applications/marketplace/image-manipulation/)

