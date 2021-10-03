---
title: Monocular depth perception
date: "2021-05-17"
tags:
  - -sa/processed
  - vision
  - -permanent
---

## Depth perception in real life

*   In nature, prey animals typically have eyes on either side of their head to maximise field of view, while most predators have forward-facing eyes with overlapping fields of vision (binocular vision) for maximum depth perception. Humans also have binocular vision.
    (Some exceptions: fruit bats, killer whales)
    
*   We perceive depth, or distance to the objects that we see, based on several visual cues.
    *   One of the cues is the [parallax](definitions/parallax.md) in the two overlapping fields of vision, or the 'binocular disparity'. ([Science Focus](bibliography/science-focus.md))
    *   However, even if vision is impaired in one eye, a human can still perceive depth by using non-binocular visual cues.
    *   In fact, according to ([Chen 2018](bibliography/chen-2018-review.md)), "a typical human uses 14 visual cues to perceive depth, only 3/14 are binocular vision related."
*   Some of the monocular cues that the brain uses: [Science Focus](bibliography/science-focus.md)
	1.  We know the real size of things
	2.  Using perspective, e.g. parallel lines converging to a perspective point
	3.  [Motion parallax](definitions/motion-parallax.md)

## Depth perception in computer vision

*   Depth is not recoverable from a single camera image.
*   This is called the "scale availability issue." s. [monocular cameras](sensors/monocular-cameras.md), whereby the scale is the factor that relates the estimated camera position to the real camera position
*   To work around this, there are several options, such as using stereo or RGBD cameras.
*   However, even if we are restricted to monocular cameras, using similar depth cues such as those used by the human brain in monocular vision can help recover scale.
    *   Some algorithms compare the obtained visual measurements to an object of known scale, e.g. using a calibration checkerboard
    *   Other algorithms make use of [motion parallax](definitions/motion-parallax.md), e.g. the [DefSLAM initialisation](SLAM/initialisation-of-monocular-slam.md)

