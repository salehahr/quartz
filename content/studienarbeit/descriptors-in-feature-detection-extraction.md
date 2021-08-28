---
title: Descriptors in feature detection/extraction
date: "2020-12-08"
tags:
  - -definitions
  - -sa/processed
  - vision
---

Source: <http://medium.com/data-breach/introduction-to-feature-detection-and-matching-65e27179885d>
Backlinks: [Bag of words](bag-of-words.md)

*   A description of the local appearance around each feature point (keypoint)
*   The descriptor encodes 'interesting' information from the image into numbers and act as an identifier ('fingerprint') to differentiate between features
*   The description should ideally be invariant to changes (such as illumination, translation, scale, in-plane rotation) so that the feature can be found again, even if the image is transformed
*   Typically: for each feature point, there is a descriptor vector

Classes of descriptors:

*   Local descriptor
    *   represents the point's local neighbourhood
*   Global descriptor
    *   describes the whole image
    *   generally not very robust—changes in parts of the image may cause the descriptor to fail

Some algorithms for feature detection/descriptor generation

*   SIFT (scale-invariant feature transform)
*   SURF (speeded up robust feature)
*   BRISK (binary robust invariant scalable keypoints)
*   BRIEF (binary robust independent elementary features)
*   [ORB](orb.md) (oriented [fast](fast.md) and rotated BRIEF)

Source: [http://en.wikipedia.org/wiki/Bag-of-words\_model\_in\_computer\_vision](http://en.wikipedia.org/wiki/Bag-of-words_model_in_computer_vision)

Feature representation using feature descriptors

*   Descriptors: vectors that represent local patches in the image
*   A good descriptor should be able to handle transformations such as rotation, intensity change, scale, etc.
*   e.g. SIFT: Scale-invariant feature transform
    *   converts a patch to a vector in 128 dimensions
    *   image as a bag of words -- image as a collection of SIFT vectors -- image as a collection of sparse numerical vector

