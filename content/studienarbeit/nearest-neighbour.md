---
title: Nearest Neighbour
date: "2020-08-06"
tags:
  - localisation/data-association
  - -sa/processed
---

Source: [SLAM for Dummies](slam-for-dummies.md)
Backlinks:  [Data association](data-association.md)

Nearest neighbour approach

1.  Get a new laser scan --> ([landmark extraction](http://www.evernote.com/shard/s484/nl/217355218/66b6bb7b-d762-4466-b392-ecf35ba5da60)) extract all visible landmarks
2.  Associate each extracted LM to the [closest LM](http://www.evernote.com/shard/s484/nl/217355218/d4f7f794-6421-4ce7-8f83-22615059a0c3) we have seen more than N times
3.  Pass each pairs of association (extracted LM, LM in database) through a [validation gate](http://www.evernote.com/shard/s484/nl/217355218/10cb7311-9aab-41b3-9ad3-15198c944b9d)
    1.  If pair passes --> n = n + 1 (num. times seen)
    2.  If pair fails --> add new LM to database, with n := 1

