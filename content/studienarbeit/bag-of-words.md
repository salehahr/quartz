---
title: Bag of words
date: "2020-11-19"
tags:
  - -sa/processed
  - vision
  - discussion/2020/2020-12
---

Parent: [SLAM Index](SLAM/slam_index.md)

Source: <http://towardsdatascience.com/bag-of-visual-words-in-a-nutshell-9ceea97ce0fb>

Has its origins in natural language processing (NLP), information retrieval

*   A text can be seen as a bag of words, with each word having different frequencies from one another
*   This can be used to compare and classify texts (similar histograms)

In vision

*   Instead of words we have features (identifying pattern in an image)
*   An image is represented as a set of features
*   Features consist of
    *   Keypoints: points that are invariant to transformation
    *   [Descriptors](descriptors.md): description of the keypoint, for feature representation
*   Construct a frequency histogram of features in the image

Workflow
Feature detection/extraction --> build vocabulary/codewords --> make histogram = BoW

Feature extractor algorithms

*   Feature detection --> desriptor extraction
*   e.g. SIFT, SURF, ORB etc. are algorithms for feature identification/description

![unknown_filename.png](./_resources/Bag_of_words.resources/unknown_filename.png)

Vocabulary building

*   Clusters are made from the [descriptors](descriptors.md)
*   Clustering algorithms, e.g. k-means, DBSCAN, etc.
*   Vocabulary (codewords) consists of the centres of each cluster
    "i.e. 1 vocab word is summarised from a group of descriptors"
    

![unknown_filename.2.png](./_resources/Bag_of_words.resources/unknown_filename.2.png)
(descriptor space)

Bag of words and comparison to other images
![unknown_filename.1.png](./_resources/Bag_of_words.resources/unknown_filename.1.png)![Image.jpg](./_resources/Bag_of_words.resources/Image.jpg)
s.  [Feature matching](feature-matching.md)

