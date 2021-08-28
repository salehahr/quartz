---
title: Geometric metric SLAM
date: "2020-07-30"
tags:
  - SLAM
  - SLAM/sparse-vs-dense
  - -sa/processed
---

Source: [Wu 2018 Image-based camera localization: an overview](wu 2018-image-based-camera-localization_-an-overview.md)
Parent: [Classification of image-based camera localization approaches](classification-of-image-based-camera-localization-approaches.md)

Computes 3D maps with accurate mathematical equations

Classification according to sensors

*   monocular
*   multiocular (most studies focus on binocular vision)
*   [multisensor fusion](multisensor-fusion.md) (e.g. vision and IMU -- vision and IMU fusion gaining in popularity)

Classification according to techniques used

*   [Filter-based SLAM](http://www.evernote.com/shard/s484/nl/217355218/2429fd5f-f22a-acc6-9f7d-d09e63206c25)
*   [Keyframe](http://www.evernote.com/shard/s484/nl/217355218/6f2315b3-3897-623d-3285-77bc7d51be76)\-based SLAM (active)
    *   Feature-based (keyframe-based feature SLAM) / sparse
    *   Direct / dense
*   Grid-based SLAM (mainly deals with laser data, deals only a bit with image data)

According to \[76\] keyframe-based can provide more accurate results compared to filter-based

*   Filter-based was common before 2010
*   Solutions after 2010 mostly based on non-filter, keyframe-based architecture

Classification according to sparse/dense (how detailed are the extracted features)

*   Feature SLAM/sparse: use points, edges etc (I think)
*   Direct SLAM/dense:
    *   detailed textured dense depth maps are produced (also: semi-dense approaches)
    *   camera pose is tracked at frame rate by entire image alignment against the dense textured model

