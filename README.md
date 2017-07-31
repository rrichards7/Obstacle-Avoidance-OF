![image001](https://user-images.githubusercontent.com/23239868/28748600-b190782c-7489-11e7-82ae-55db54c94050.jpg)
# Autonomous Snomobile Obstacle Avoidance using Optical Flow Curl Analysis #

*Lead Architect: Ryan J. Richards*

*The Pennsylvania State University - School of Electrical Engineering and Computer Science*

## Introduction/Methodology ##

Optical Flow is the motion of objects, surfaces, edges, etc in a scene computed by a current and previous frame. The Lucas-Kanade (LK) differential method is a widley used way for computing optical flow. This method is available on both LabVIEW's IMAQ libraries and OpenCV libraries. 

Studies have been conducted for testing the effectiveness of optical flow for obstacle detection and avoidance **([1], [2], ...)**. All have their own unique advatages and drawbacks. 

A new method is proposed and tested which utilizes a curl-based analysis of optical flow to detect obstacles. The curl of each velocity field (two-components) are computed. The 2D field is filtered by value and each remaining object is dilated using a basic morphological technique. The objects then undergo a particle analysis (ultimately used for the ROI highlighting process).

## LabVIEW Code ##


## Appendix ##
