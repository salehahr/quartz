---
title: defSLAM::System constructor
date: "2020-10-21"
tags:
  - -sa/processed
  - SLAM/algos/DefSLAM
---

Parent: [DefSLAM simple\_camera](defslam-simple__camera.md)

defSLAM::System::System(const string &strVocFile, const string &strSettingsFile,
 const bool bUseViewer)
:   mSensor(MONOCULAR),
 mpLoopCloser(NULL),
 mpViewer(static\_cast<Viewer  \*>(nullptr)),
 mbReset(false),
 mbActivateLocalizationMode(false),
 mbDeactivateLocalizationMode(false)

Constructor
// initialise mpVocabulary from file
// create mpKeyFrameDatabase from mpVocabulary
// create map DefMap()
// create drawers for viewer DefFrameDrawer DefMapDrawer
// initialise tracking, mapping, viewer threads; loop closing not implemented in DefSLAM
mpTracker = new DefTracking(...);
mpLocalMapper = new DefLocalMapping(...); 
mpViewer = new DefViewer(...);

Attributes
eSensor mSensor
ORBVocabulary \*mpVocabulary
KeyFrameDatabase \*mpKeyFrameDatabase
Map \*mpMap // stores pointers to all KFs, all MapPoints

Tracking \*mpTracker         // receives Frame, computes camera pose Tcw, KF insertion
LocalMapping \*mpLocalMapper // local map management, local BA
LoopClosing \*mpLoopCloser   // search for loop every KF. if there is a loop, do PGO, full BA

Viewer \*mpViewer
FrameDrawer \*mpFrameDrawer;
MapDrawer \*mpMapDrawer;
// Threads
// tracking thread in main execution
std::thread \*mptLocalMapping;
std::thread \*mptLoopClosing;
std::thread \*mptViewer;
std::mutex mMutexReset;
bool mbReset;
std::mutex mMutexMode;
bool mbActivateLocalizationMode;
bool mbDeactivateLocalizationMode;
std::mutex mMutexState;
std::mutex mMutexdata;

a

