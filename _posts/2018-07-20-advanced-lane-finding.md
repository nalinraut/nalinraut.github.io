---
layout: projects
title:  "Advanced Lane Finding"
duration:  "July 2018" 
excerpt: "Computer Vision"
project: true
---

[//]: # (Image References)

[image1]: ./assets/img/lanefinding/project_video.gif "Final Output"
[image2]: ./assets/img/lanefinding/calibration.png "Process of camera calibration."
[image3]: ./assets/img/lanefinding/undistorted.png "Original and Undistorted Images."
[image4]: ./assets/img/lanefinding/warped.png "Warped and Unwarped Images."
[image5]: ./assets/img/lanefinding/threshold.png "Combined gradient and color threshold."
[image6]: ./assets/img/lanefinding/histogram.png "Histogram"
[image7]: ./assets/img/lanefinding/windows.png "Sliding Window"
[image8]: ./assets/img/lanefinding/lane.png "Lane"

[image9]: ./assets/img/lanefinding/curve.png "curve"

[image10]: ./assets/img/lanefinding/test2.png "test"
[image11]: ./assets/img/lanefinding/test3.png "test"
[image12]: ./assets/img/lanefinding/test3.png "test"

---
![][image1]
<br/>
<center><h3>Description</h3></center>
<hr class="star-primary">
<p style="text-align: justify"> When we drive, we use our eyes to decide where to go. The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle. In this project, I develop an algorithm to detect lane lines automatically with a front facing camera. This project is an upgrade to</p> 

[Finding Lane Lines Road](https://nalinraut.github.io/finding-lane-lines/).<br/>
<p>Programming platform and Libraries: Python and OpenCV.</p>


<center><h3>Methodology</h3></center>
<hr class="star-primary">
<!-- <p style="text-align: justify">Firstly, a valid maze is generated using Depth-First Search Algorithm.
                            Further, robot follows the undermentioned policy,<br/>
                            • Each robot starts exploring those cells which have not been previously explored by itself  and any other robots.<br/>
                            • While exploring, if a robot detects a junction which is a cell with two or more branches, the robot arbitrarily chooses a direction for further exploration and stores the junction as potentially unexplored node.<br/>
                            • While exploring the maze, if the robot encounters a dead-end or enters a cell already explored by another robot, the robot back-tracks to the nearest unexplored cell.<br/>
                            • All robots continue their exploration until all potentially unexplored cells in their respective lists are visited.<br/>
                            • Since all robots are continuously communicating with the common server, they get the completely mapped maze in the end which will further be used to travel to the goal node.<br/></p> -->


#### (i) Camera Calibration and Lens Distortion Correction

For camera calibration and lens distortion correction I created a class called Camera
 - `camera = Camera(directory = 'camera_cal/')`initializes the Camera object with the calibration image files
 - `camera.calibrate()` This method uses the loaded images and computes `mtx`- the camera matrix and `dist`- the distortion coefficients using  `cv2.calibrateCamera()`. This requires `objpoints` and `imgpoints` which are computed using `cv2.findChessboardCorners`. `mtx` and `dist` are made into a dictionary and saved as a pickle object `camera_calib.p`.
 - `camera.getCalibration()` method loads the calibration file.
 - `camera.undistort()` is used for correcting the lens distortion in an image.
 
 The images below shows the process of calibration with original and undistorted images.

 ![alt text][image2]
 ![alt text][image3]







#### (ii) Perspective Transform
For obtaining a perspective transform of an image I created the class Transform
- The `getPoints()` method yields source and destination points for the given image.
- `getPerspectiveTransform()` and `getInversePerspectiveTransform()` yields warped and unwarped images respectively.

The code below outputs source and destination points.

```python
        offset = 75
        src_pts = np.float32([[w // 2 - offset, h* 0.625], 
                          [w // 2 + offset, h * 0.625], 
                          [offset, h], 
                          [w - offset, h]])

        dst_pts = np.float32([[offset, 0], 
                          [w - offset, 0], 
                          [offset, h], 
                          [w - offset, h]])
 ```
The figure below shows warped and unwarped images.
![alt text][image4]


#### (iii) Combined gradient and color thresholds
I created the Threshold class for applying combined gradient and color thresholds.
The image is converted into HSL space to identify the yellow and white portions since lanes fall into the same color spectrum (Lanes are either white or yellow in color)
In addition to the HSL space, Sobel filter in 'x' direction is applied to image since the filter in 'x' direction detects edges close to horizontal. 
The figure below shows images with gradient and color thresholds in a combination. The green color in the stacked image represents the gradient threshold region and blue color represents the color threshold. 
![alt text][image5]



#### (iv) Identifying lane line pixel points

To identify the lane pixels, first we compute the histogram so we know where the lane lines originate and follow them or trace them using sliding windows. I used the sliding window approach to compute the first set of curves and then just used the previous curve parameters to detect new curves.
The figure below shows a histogram with two peaks where the lane lines originate. 
![alt text][image6]

Below is the image showing sliding windows. The sliding windows finds pixel points foe lane lines and fits a polygon.
![alt text][image7]

The figure below shows poynomilas fit to the pixel points. The lane line in the next frames except for the first one are depicted using the polynomals on the first frame. Also, the lane is sketchedout between the left and right lane lines.
![alt text][image8]



#### (v) Radius of Curvature
To find the radius of curvature I use the following equations

![alt text][image9]


<!-- #### Video

Link to the video:

Here's a [link to my video result](./project_video_output.mp4) -->



#### Examples
![alt text][image10]

![alt text][image11]

![alt text][image12]



<center><h3>Conclusion</h3></center>
<hr class="star-primary">

<p style="text-align: justify"> The method is slow and not robust. Semantic segmentation techniques can be used to identify drivable areas and lane lines. </p>

<hr class="star-primary">
                            
<ul id ="horizontal-list">
<li class="display: inline">
<strong><a target="_blank"  href="https://github.com/nalinraut/CarND-Advanced-Lane-Finding">Code Repository Link <i class="fa fa-fw fa-github"></i></a>
</strong>
</li>
                                
                                
<!-- <li>
<strong><a href="javascript:void(0);">Project-Report</a>
</strong>
</li> -->
                                
</ul>
     

