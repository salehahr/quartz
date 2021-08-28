---
title: DefTracking::Track
date: "2020-10-21"
tags:
  - -sa/processed
  - SLAM/algos/DefSLAM
---

Parent: [Tracking::GrabImageMonocular](tracking__grabimagemonocular.md)

void DefTracking::Track
// if: not initialised, do: [monocular initialisation](http://www.evernote.com/shard/s484/nl/217355218/b32ef55f-1e31-486d-8a80-9dfd4226618e)
// elseif: already initialised, do: track frame
{
 // if: tracking and mapping, do:
 bOK = [TrackWithMotionModel](http://www.evernote.com/shard/s484/nl/217355218/b44c4be7-f66b-4739-90da-6710241bae2e)();

 // if bOK (there exists camera pose estimate and matching), track local map
 // if template is updated (keyframe-rate update)
 set reference KF from new template
 do [DefPoseOptimization](http://www.evernote.com/shard/s484/nl/217355218/9a19739f-c04f-4008-8822-d782ed4f5e2a)(...);
 bOK = TrackLocalMap();

 // if: bOK, update motion model (update mVelocity); clean VO matches
 // check if we should insert a new KF, delete outliers for BA

}

