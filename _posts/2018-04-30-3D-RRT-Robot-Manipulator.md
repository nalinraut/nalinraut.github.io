---
layout: post
title:  "3 Dimensional Rapidly Exploring Random Trees Algorithm on Fetch Robot"
excerpt: "Motion Planning"
project: true
duration: "April 2017 - May 2017"
---

![image-title-here](/assets/img/mp1.gif){:class="img-responsive width=176 height=71"}   
<br/>

<center><h3>Description</h3></center>
<hr class="star-primary">
<p style="text-align: justify"> This project uses Open AI's Robotics Environment for a Motion Planning problem. Rapidly exploring Random Trees (RRT) algorithm is implemented in a 3- Dimensional Space. Motion planing algoritm is implemented in the Fetch Robot Manipulator and the end-effector follows the planned path from a start to goal location. </p>


<center><h3>Methodology</h3></center>
<hr class="star-primary">
<p style="text-align: justify">
• Implemented 3-Dimensional RRT in a 3D space.<br/>
• Initiated the space with start and goal location.<br/>
• Fed the obtained path to the OpenAI’s Gym and made the end    effector follow both the extend and connect version of RRT.<br/>
• Observed the path followed by the end effector in the space with and without obstacle.<br/>
• Computed the total cost of both extend and connect path for spaces with and without obstacles.<br/>
</p>


<h3>Results</h3>
<hr class="star-primary">
<p style="text-align: justify"> We compare the cost of both paths, the generated one and the followed one. Ofcourse, the robot won't take the generated path because it is generated and more complex. It would rather follow a simple path with minimum breaks.<br/><br/></p>

<p style="text-align: justify">The figure below shows both, 1. The path randomly generetaed in red, and 2. The path followed in green for 3 dimensional space without any obstacles.</p><br/><br/>

![image-title-here](/assets/img/3drrt1.png){:class="img-responsive width=176 height=71"} <br/><br/>

<p style="text-align: justify"> The table below shows cost incurred for paths in a 3D space without obstacle.</p>

![image-title-here](/assets/img/3drrt1r.png){:class="img-responsive width=176 height=71"} <br/><br/>

<p style="text-align: justify;">The figure below shows both, 1. The path randomly generetaed in red, and 2. The path followed in green for 3 dimensional space with obstacle.</p><br/><br/>

![image-title-here](/assets/img/3drrt2.png){:class="img-responsive width=176 height=71"} <br/><br/>

<p style="text-align: justify"> The table below shows cost incurred for paths in a 3D space with obstacle.</p>

![image-title-here](/assets/img/3drrt2r.png){:class="img-responsive width=176 height=71"} <br/><br/>

<hr class="star-primary">
                            
<ul class="list-inline item-details">
                                
<li>
<strong><a target="_blank"  href="https://github.com/nalinraut/Planning-Algorithms/tree/master/3D_RRT">Code Repository Link <i class="fa fa-fw fa-github"></i></a>
</strong>
</li>
<li>
<strong><a href="https://github.com/nalinraut/Planning-Algorithms/blob/master/3D_RRT/Report.pdf">Project-Report</a>
</strong>
</li>
</ul>
     

