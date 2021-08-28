---
title: Program outline
date: "2021-07-07"
tags:
  - to-do
  - to-do/orphan
  - -sounding-board
  - -sa/processed
  - discussion/2021/2021-07
---

Current assumptions (to take care of later!)

*   [x] Probe is rigid — DOFs are either 0 or constant — switch to rotating scope later
*   ~~No gravity~~
*   ~~No bias/offset, no noise in IMU~~

* * *

Note: Stuff marked with checkboxes are either to-dos or things I'm not sure that I implemented correctly

<http://github.com/feudalism/dvi-ekf/tree/eskf>; [projects](http://github.com/feudalism/dvi-ekf/projects)

generate\_data.py
Data generation (is called from main.py)

Main objects

*   Generate camera data (from DefSLAM mono trajectory)
*   Make RigidSimpleProbe (for now, all DOFs are 0 or constant)
*   Make IMU object, generate first (om, acc) values from interpolated camera data ( - [x] should generate it from stereo data instead)

Variables

*   Initial states x0 (initial IMU pose, initial IMU velocity initial IMU dofs, initial camera pose)
    *   Generated from camera data at t=0
    *   Initial IMU pose = initial camera pose + relative pose B->C from probe (dependent on DOFs)
*   Initial covariance matrix P0
*   Noise matrices Q and R (to do: [x] perform generation inside Filter itself, so that the entries can be updated with Filter.dt)

* * *

main.py
Initialisation of Kalman filter

*   Set initial states and covariance: x0, P0
*   Set values in buffer: imu.om, imu.acc, R\_WB (- [x] maybe I should include p\_B in the buffer, for p\_cam prediction)
*   Append initial states to Trajectory (for plotting)
*   Set noise matrices from stdev values ( [x] as stated above, to be moved to an internal Filter function!)

Filter main loop
Iterate over camera images

*   Propagate stage
    *   Get queue of interpolated camera data  (from old\_t up till current t, i.e. from previous 'real' camera data up till current 'real' camera data)
        (- [x] would probably be faster to pre-generate the fake IMU data to a text file and read from it for the current test case using RigidSimpleProbe — I only implemented it this way because I might want to update the probe DOFs later on, which would affect the IMU data to be generated, s. next checkbox below)
        
    *   Iterate over queue of interpolated camera data
        *   Fake data gen: evaluate (om, acc) values based on:
            *   joint dofs ([x] here I use the initial DOFs for the entire loop; later to update according to the estimated DOFs?)
            *   interpolated camera data
        *   Perform state propagation
            *   Predict nominal state, ref. eqns in [IMU nominal-state and error-state kinematics](imu-nominal-state-and-error-state-kinematics.md)
                x\_next = f(t, x, u)
                
            *   Predict error state
                *   calculate Fx, ref.  [IMU ESKF prediction equations](imu-eskf-prediction-equations.md)
                *   redundant: err\_x\_next = Fx \* err\_x = 0 (because initial err\_x is zero)
            *   Predict covariance
                ![Image.png](./_resources/Program_outline.resources/Image.png)
                for calculating Fi matrix, see [IMU ESKF prediction equations](imu-eskf-prediction-equations.md)
                
        *   Update buffer
        *   Append current state to Trajectory (for plotting)

*   Update stage
    *   Get current camera data (pos, rot)
    *   [x] to do for later when using a non-rigid probe: compensate for notch angular displacement 
    *   Compute gain using H matrix, ref. [H Jacobian matrix in the ESKF filter correction](h jacobian matrix-in-the-eskf-filter-correction.md)
    *   Compute residuals
    *   Compute error states: err = K @ residuals
    *   Correct the nominal states according to the respective composition rules, ref. [Variables in ESKF](variables-in-eskf.md)
    *   Calculate covariance, ref. [Filter correction](filter-correction.md)
    *   \--> next loop iteration

Plot
- [x] I still need to make a proper plot function where we can see all the states
- [x] Maybe also a 3D plot

