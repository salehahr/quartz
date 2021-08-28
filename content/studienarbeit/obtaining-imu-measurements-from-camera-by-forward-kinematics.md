---
title: Obtaining IMU measurements from camera by forward kinematics
date: "2021-06-11"
tags:
  - -sa/processed
  - math/kinematics
  - discussion/2021/2021-06
  - discussion/2021/2021-07
---

Parent: [SA TODO](sa-todo.md)
Backlinks: [Thesis restructure](thesis-restructure.md)

Done:
- [x] [reverse-fwkin](reverse-fwkin.md) (scrapped)
- [x] omega\_B symbolic
- [x] check links in BC and CB config — new diagrams (split up into >=2 bodies?)
- [x] check om\_B = om\_C + om\_CB (s. [http://en.wikipedia.org/wiki/Denavit%E2%80%93Hartenberg\_parameters
- Kinematics](http://en.wikipedia.org/wiki/Denavit%E2%80%93Hartenberg_parameters
- Kinematics), [Woernle](woernle.md))
- [x] save om\_B to container
- [x] obtain accel. (s. [http://en.wikipedia.org/wiki/Denavit%E2%80%93Hartenberg\_parameters
- Kinematics](http://en.wikipedia.org/wiki/Denavit%E2%80%93Hartenberg_parameters
- Kinematics),  [Kinematics primer](kinematics-primer.md))
    ![6323bb657b9f82d520ad13e7d86fc612160d7a78](http://wikimedia.org/api/rest_v1/media/math/render/svg/6323bb657b9f82d520ad13e7d86fc612160d7a78)
    where  ![e502f568baa4e4d91f1733ea1f5f2ec0d0d41b42](http://wikimedia.org/api/rest_v1/media/math/render/svg/e502f568baa4e4d91f1733ea1f5f2ec0d0d41b42) (ang. vel of body j w.r.t. body i, expressed in CS k)
    ![581c4001a22f55cf57844a8861d0901827e4f267](http://wikimedia.org/api/rest_v1/media/math/render/svg/581c4001a22f55cf57844a8861d0901827e4f267)

    Chaining velocities and accelerations:
    ![unknown_filename.png](./_resources/Obtaining_IMU_measurements_from_camera_by_forward_kinematics.resources/unknown_filename.png)
- [x] \[validation\] reconstruct rot\_B from om\_B, compare with camera
- [x] debug first reconstruction of IMU traj, if that doesn't work debug the fake data generation
    - [x] update readme
- [x] update robot model with simplification around pivot point
- [x] validate updated model

Anhang
![unknown_filename.1.png](./_resources/Obtaining_IMU_measurements_from_camera_by_forward_kinematics.resources/unknown_filename.1.png)

