---
title: DefOptimizer::poseOptimization
date: "2020-10-21"
tags:
  - -sa/processed
  - SLAM/algos/DefSLAM
---

Parent: [DefTracking:TrackWithMotionModel()](deftracking_trackwithmotionmodel().md)

int DefOptimizer::poseOptimization(Frame \*pFrame)

// Set estimate of solution to current camera pose
g2o::VertexSE3Expmap \*vSE3 = new g2o::VertexSE3Expmap();
 vSE3->setEstimate(Converter::toSE3Quat(pFrame\->mTcw));
 vSE3->setId(0);
 vSE3->setFixed(false);
 optimizer.addVertex(vSE3);

// Set MapPoint vertices (num. nodes in opt. graph?)
  const int N = pFrame\->N;

