---
title: unet-paper
date: 2022-04-25
tags:
  - ma
---

**Source**: U-Net paper

## Contributions
* Architecture + training strategy using data augmentation
* Best performing network on ISBI challenge for segmentation of structures in microscopy images, cell tracking in microscopy images


## History
* Up till now, CNN mainly for image classification: image --> single label
* Problems in biomedical image processing
    * localisation also necessary: which class label belongs to which pixel?
    * sparse dataset (not enough annotated data)
* Ciresan: network in sliding window setup to predict pixel class label
    * provides patch around pixel as input
    * localisation is successful
    * training data in patches > training data as images themselves (1 image --> many patches)
    * drawbacks:
        * slow, NW run separately for each patch
        * redundancy: overlapping patches
        * trade-off between localisation accuracy and use of context
            * better localisation: small patches, but NW sees little context (bad for classification)
            * better context: large patches, but max pooling layers reduce localisation accuracy

## Idea
Want both: localisation accuracy, and classification accuracy (use of context)
* For context: use features from multiple layers --> skip connections
* Pooling is replaced by upsampling --> increase resolution of the output
    * We want learnable upsampling
    * In U-Net: reason for this is because they want to propagate context from lower res to higher res layers 
* For localisation: high rest features from contracting path are combined with upsampled inputs
* Tiling strategy: for dealing with large images that won't fit on the GPU
    * "Output segmentation map only contains the pixels, full context for the segmap is available in the input image."
    * Prediction of the segmentation outputs a smaller image (yellow) than given as input (blue) -- "pred of yellow area requires blue are a as input"   
        ![](_img/unet-tile.png)
* (also instance segmentation, separation of touching cells)


## Architecture
* Symmetric contractive path and expansiv path
* Contractive (encoder) path:
    * two 3x3 convolutions (unpadded) --> ReLU --> 2x2 max pooling (s=2)
    * At each downsampling, f:=2f_prev
    * Captures context of image by producing feature maps -- https://medium.datadriveninvestor.com/an-overview-on-u-net-architecture-d6caabf7caa4?gi=8e31c4ea65de
* Expansive (decoder) path:
    * Upsampling??? --> 2x2 up-conv + skip (cropped version of feature map from expansive map, need cropped version due to loss of border pixels)
    * Enables localisation by increasing resolution and taking in feature map (context) from previous level -  -- https://medium.datadriveninvestor.com/an-overview-on-u-net-architecture-d6caabf7caa4?gi=8e31c4ea65de
* Final layer: 1x1 convolution to map each of the 64 final feature maps to the desired number of classes
* 23 convolutional layers
* No dense layers, so images of arbitrary input size can be used (only params. to be learned are kernels)


## Questions
* [ ] What does use of context mean?  
    Use of surrounding 'patch' of image
    
## Notes
https://towardsdatascience.com/understanding-semantic-segmentation-with-unet-6be4f42d4b47
* Regular CNN: we get class 'what?' but lose the location information 'where' -- pure classification
* What is wanted: semantic segmentation: what + where/which pixels