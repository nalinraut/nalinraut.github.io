---
title: "3 Dimensional Rapidly Exploring Random Trees Algorithm on Fetch Robot"
excerpt: "Motion Planning - April 2017 - May 2017"
collection: portfolio
---

![3D RRT]({{ '/assets/img/mp1.gif' | relative_url }}){:style="max-width: 500px; height: auto;"}

## Description

This project uses Open AI's Robotics Environment for a Motion Planning problem. Rapidly exploring Random Trees (RRT) algorithm is implemented in a 3- Dimensional Space. Motion planning algorithm is implemented in the Fetch Robot Manipulator and the end-effector follows the planned path from a start to goal location.

## Methodology

* Implemented 3-Dimensional RRT in a 3D space.
* Initiated the space with start and goal location.
* Fed the obtained path to the OpenAI's Gym and made the end effector follow both the extend and connect version of RRT.
* Observed the path followed by the end effector in the space with and without obstacle.
* Computed the total cost of both extend and connect path for spaces with and without obstacles.

## Results

We compare the cost of both paths, the generated one and the followed one. Of course, the robot won't take the generated path because it is generated and more complex. It would rather follow a simple path with minimum breaks.

The figure below shows both, 1. The path randomly generated in red, and 2. The path followed in green for 3 dimensional space without any obstacles.

![3D RRT 1]({{ '/assets/img/3drrt1.png' | relative_url }}){:style="max-width: 500px; height: auto;"}

The table below shows cost incurred for paths in a 3D space without obstacle.

![3D RRT 1 Results]({{ '/assets/img/3drrt1r.png' | relative_url }}){:style="max-width: 500px; height: auto;"}

The figure below shows both, 1. The path randomly generated in red, and 2. The path followed in green for 3 dimensional space with obstacle.

![3D RRT 2]({{ '/assets/img/3drrt2.png' | relative_url }}){:style="max-width: 500px; height: auto;"}

The table below shows cost incurred for paths in a 3D space with obstacle.

![3D RRT 2 Results]({{ '/assets/img/3drrt2r.png' | relative_url }}){:style="max-width: 500px; height: auto;"}

**Code Repository:** [GitHub](https://github.com/nalinraut/Planning-Algorithms/tree/master/3D_RRT)  
**Project Report:** [PDF](https://github.com/nalinraut/Planning-Algorithms/blob/master/3D_RRT/Report.pdf)

