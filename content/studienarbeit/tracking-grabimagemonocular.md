---
title: Tracking_GrabImageMonocular
date: "2020-10-21"
tags:
  - -sa/processed
  - SLAM/algos/DefSLAM
---

Parent: [defSLAM::System::TrackMonocular](defslam-system-trackmonocular.md)

cv::Mat ORB\_SLAM2::Tracking::GrabImageMonocular

*   colour conversion
*   make frame using image, timestamp, ORB stuff, calibration data, etc.
    mCurrentFrame = new [Frame](http://www.evernote.com/shard/s484/nl/217355218/f943b3a2-8f95-47c1-a716-4f8aedd164e3)(mImGray, timestamp, mpORBextractorLeft,
    

 mpORBVocabulary, mK, mDistCoef, mbf, mThDepth, im)

*   perform tracking: [Track](http://www.evernote.com/shard/s484/nl/217355218/f08bea14-abcd-44e3-898e-d138d730160f)();
*   return camera pose
    return mCurrentFrame->mTcw.clone();

