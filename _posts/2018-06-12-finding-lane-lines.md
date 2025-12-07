---
layout: post
title:  "Finding Lane Lines on Road"
duration:  "June 2018" 
excerpt: "Computer Vision"
project: true
---

[//]: # (Image References)

[image0]: /assets/img/lanelines/video.gif
[image1]: /assets/img/lanelines/hsv_img.png
[image2]: /assets/img/lanelines/gray_img.png
[image3]: /assets/img/lanelines/gray_blur.png
[image4]: /assets/img/lanelines/edges.png
[image5]: /assets/img/lanelines/roi1.png
[image6]: /assets/img/lanelines/extrapolated.png
[image7]: /assets/img/lanelines/final_extrapolate.png
[image8]: /assets/img/lanelines/image.jpg

---
![][image0]
<br/>
<center><h3>Description</h3></center>
<hr class="star-primary">
<p style="text-align: justify"> When we drive, we use our eyes to decide where to go. The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle. In this project, I develop an algorithm to detect lane lines automatically.<br/>
Programming platform and Libraries: Python and OpenCV.</p>


<center><h3>Methodology</h3></center>
<hr class="star-primary">
<!-- <p style="text-align: justify">Firstly, a valid maze is generated using Depth-First Search Algorithm.
                            Further, robot follows the undermentioned policy,<br/>
                            • Each robot starts exploring those cells which have not been previously explored by itself  and any other robots.<br/>
                            • While exploring, if a robot detects a junction which is a cell with two or more branches, the robot arbitrarily chooses a direction for further exploration and stores the junction as potentially unexplored node.<br/>
                            • While exploring the maze, if the robot encounters a dead-end or enters a cell already explored by another robot, the robot back-tracks to the nearest unexplored cell.<br/>
                            • All robots continue their exploration until all potentially unexplored cells in their respective lists are visited.<br/>
                            • Since all robots are continuously communicating with the common server, they get the completely mapped maze in the end which will further be used to travel to the goal node.<br/></p> -->
### The Pipeline
My pipelines consists of the following steps:

#### (i) Converting the input image to HLS from RGB: 
The <i>toHLS()</i> function converts the image to HLS scale and masks the image with yellow and white filters. The HLS       domain takes care of the variation in the lighting conditions.




![HLS Image][image1]


#### (ii) Converting the HSL masked image to grayscale:
The image is further converted into an grayscale image.



![Grayscale][image2]

#### (iii) Applying Guassian Blur:
Further, a Guassian Blur filter with kernel size 15 is used to remove noise.



![Gaussian Blur][image3]

#### (iv) Perform Canny Edge Detection:
Next the grayscaled image is fed into a canny edge detector and edges are obtained. A double threshold is used (low threshold = 100 and high threshold = 200) with low threshold to high threshold ratio between 1/2 p 1/3 as suggested.



![Canny][image4]

#### (v) Extract Region of Interest:
Edges are detected all over the image, however, the edges that matter are in a particular region therefore the polygonal region is extracted and only those edges that fall in that region are kept while rest are discarded.



![Canny with RoI][image5]

#### (vi) Draw Hough Lines on the Edge Image:
The image with edges is used to draw Hough lines. The function basically converts the points in the image space to lines inthe Hough space. For drawing lines I use the <i>modified_draw_lines()</i> function to ensure several line segments are extrapolated/ averaged to one line segment per lane line, also ensuring the smoothness.
The raw line segments (more than one per lane line) are broken and need to be averaged as well as extrapolated and for this, I find the slope of each line segment and further classify the points on the line segments to be part of either positive slope or negative slope. Here the line segments with positive slope belong to the right lane line and line segments with negative slope belong to the left lane line. To fit a line, <i>polyfit()</i> with 1 degree is used and further the lane lines are drawn. A global list with a fixed length is maintained to which the coordinates are appended. This helps the algorithm to also keep track of previous points. This way, the broken lines can be extrapolated/ averaged to a single line.



![Extrapolate][image6]

#### (vii) Extract Region of Interest:
Again, the extrapolated lane lines are drawn on the entire image. To avoid this a region of interest masks the image for the lane lines appear only in the region that matters.



![Extrapolate with RoI][image7]

#### (viii) Weighted Image:
The image with extrpolated lines goes on the original image and forms the final image.



![Final Image][image8]

<!-- <center><h3>Results</h3></center>
<hr class="star-primary">
<p style="text-align: justify"> </p> -->



<center><h3>Conclusion</h3></center>
<hr class="star-primary">

<p style="text-align: justify"> This project is a very primitive way of detecting lane lines. The shortcoming of this project is the need to manually tune a number of parameters that can be done using auto-calibration. Also, the algorithm can be improved using a quadratic curve fitting techinique encompassing the edge points. This will provide with better results. </p>

<hr class="star-primary">
                            
<ul id ="horizontal-list">
<li class="display: inline">
<strong><a target="_blank"  href="https://github.com/nalinraut/CarND-Lane_Lines">Code Repository Link <i class="fa fa-fw fa-github"></i></a>
</strong>
</li>
                                
                                
<!-- <li>
<strong><a href="javascript:void(0);">Project-Report</a>
</strong>
</li> -->
                                
</ul>
     

