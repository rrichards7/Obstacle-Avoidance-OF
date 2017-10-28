![image001](https://user-images.githubusercontent.com/23239868/28748600-b190782c-7489-11e7-82ae-55db54c94050.jpg)
# Autonomous Snomobile Obstacle Avoidance using Optical Flow Curl Analysis #

*Lead Architect: Ryan J. Richards*

*The Pennsylvania State University - School of Electrical Engineering and Computer Science*

## Introduction/Methodology ##

Optical Flow is the motion of objects, surfaces, edges, etc in a scene computed by a current and previous frame. The Lucas-Kanade (LK) differential method is a widley used way for computing optical flow. This method is available on both LabVIEW's IMAQ libraries and OpenCV libraries. 

Studies have been conducted for testing the effectiveness of optical flow for obstacle detection and avoidance **([1], [2], [3])**. All have their own unique advatages and drawbacks. 

A new method is proposed and tested which utilizes a curl-based analysis of optical flow to detect obstacles. The curl of each velocity field (two-components) are computed. The 2D field is filtered by a user-defined value and each remaining object is dilated using a basic morphological technique. The objects then undergo a particle analysis (ultimately used for the ROI highlighting process).

## LabVIEW Code ##

This curl-analysis is realized using LabVIEW's IMAQ library. This VI allows the user to enter a folder containing frame-by-frame images of a video. The VI then analyzes and computes the Optical Flow for each frame (and the previous one). The user can then view the results in the main image indicator, while viewing an intensity graph of the velocity curl-field on a separate indicator. To use this VI follow these steps:

(1) enter the folder containing images of the video in the **Video Sequence Folder Path**

(2) press the **run** button and watch the video/analysis execute

(3) if the user wants to stop at anytime during the analysis then press the **STOP** button

![2](https://user-images.githubusercontent.com/23239868/28973013-f33eaaee-78ff-11e7-8c72-ef6c40e116e4.JPG)


## Results ##

Extensive testing revealed that this algorithm is a suitable (albeit slightly computationally time consuming) way of detecting obstacles in snowy conditions. The figure below shows the obstacles being detected in the blue region-of-interest (ROI) boxes, while the LK velocity vectors are the red arrows.

![1](https://user-images.githubusercontent.com/23239868/28973012-f33a6ace-78ff-11e7-930b-b14deb7ae21c.JPG)


## Appendix ##

[1] https://github.com/tgarc/flownav

[2] http://opticflow.bu.edu/research/time-to-contact-estimation

[3] http://www.cs.cornell.edu/~asaxena/rccar/icml_obstacleavoidance.pdf
