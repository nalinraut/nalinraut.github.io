---
layout: projects
title:  "Virtual Haptic Environment"
duration: "January 2018 - May 2018" 
excerpt: "Robot Dynamics"
project: true
---

![image-title-here](/assets/img/dyn.gif){:class="img-responsive width=176 height=71"}   
<br/>
<center><h3>Description</h3></center>
<hr class="star-primary">
<p style="text-align: justify">With the advancement of technology, robot assisted surgical systems are developed to overcome the limitations of pre-existing minimally-invasive surgical procedures. However, these surgical systems lack real time force feedback during the operation. Haptics and force feedback allow a surgeon to make more controlled movements in simulation and reality, but so far neither has been extensively implemented. This paper aimed to model a virtual gripper to interact with dynamic bodies present in the environment and calculate simulated tip forces to transfer back to the haptic device and subsequently the user. The force feedback produced at the gripper is translated to the haptic device, enabling the user to feel the forces generated at the gripper. The simulated environment, dynamical calculations, and feedback were tested using the haptic device controlling the modelled gripper by holding, moving, and acting upon bodies present in the virtual environment.</p>


<center><h3>Methodology</h3></center>
<hr class="star-primary">
<p style="text-align: justify">
The idea of virtual haptic environment for surgical simula-
tion has been realized through the integration of several open
source softwares, the most crucial of them being CHAI3D,
ROS, OpenGL, and Bullet Physics engine. Chai3D is the most
effective haptic research software which has been integrated
with ROS to establish communication between the virtual
haptic environment and the physical haptic devices like da
vinci , Geomagic Touch and Novint Falcon. The CHAI3D
library internally uses OpenGL and Bullet physics engine
to model the computer graphics and simulate the physics
respectively. A high level OpenGL wrapper library called
GLFW has been used to develop the modules and virtual
environments as it allows easy usage of the rather complex
OpenGL library. The Bullet physics engine was used to model
the physical interactions between the objects for example in
the pick and place module discussed in the section IV-C.
The CHAI3D library automatically identifies the haptic
devices connected to the computer and spawns the tool in the
virtual environment which is set while developing the module.
Specifically for the MTM(master tool manipulator) of DVRK,
the tool that represents the haptic device in the environment is
a gripper as shown in Fig. 6. This gripper mimics the MTM
and can be opened and closed by pinching action performed
on the MTM. The haptic tool used for the Geomagic touch
device for the purpose of incision practice is a knife or a thin
surgical tool as mentioned in section IV-B as the manipulator
of Geomagic touch is a stylus having 6 Degrees of Freedom.
For establishing the communication between Novint Fal-
con and CHAI-ROS bridge, ros-falcon Catkin package was
installed along with the device drivers. Although CHAI3D
detects to Novint Falcon automatically, this ROS package
allows the Falcon to interact with the virtual DVRK as the
DVRK library has been developed as a ROS package. This
package allowed the easy manipulability of gripper using the
Falcon device while receiving accurate haptic feedback. The
pick and place module discussed in section IV-C relies upon
the falcon device with the modified gripper design.
Using the Geomagic touch device with CHAI3D is a
challenge as the device is old and not supported directly
by the CHAI3D library. Although there exists procedures to
install the device kernels for the CHAI environment to detect
it, we were unsuccessful in doing so because of operating
system compatibility issues. Also, the native kernel would
not provide ROS interfacing. To tackle this situation, the
Geomagic ROS package was installed and a teleoperation
module was developed from scratch to interface the Geomagic
touch with the virtual MTML device in the haptic simulation.
The Geomagic ROS package provides the ROS topics for pose,
force and twist that were used to establish its communication
with the MTML as the DVRK ROS package provides similar
ROS topics. This module aided us in realizing the incision
practice task as discussed in section IV-B.
Fig 5 shows the high level architecture of all the developed
modules tied together establishing communication between the
devices. The gt talker ROS node interfaces the Geomagic
touch and virtual MTML kinematics whereas gt force is
responsible for transmitting the force feedback from the virtual
environment to the Geomagic Touch physical device. Although
the kinematics teleoperation worked as expected after scaling
down the device workspace to fit in the virtual environment,
the force feedback received was inaccurate and inconsistent
because of the control law that need to be rewritten in order
to allow accurate force feedback to the user while using
Geomagic device in the incision practice module that was
created in this project.
The ROS topics at the left-most side shoes the nodes for
keyboard teleoperation. The chai env node is the main ROS
node that interfaces CHAI3D with ROS-DVRK that allows the
haptic devices to interact with the virtual gripper and knife
tools in the CHAI3D environment.
The ROS wrapped architecture is highly flexible in terms of
programming languages and provides lot of useful function-
alities otherwise unavailable. It allows the inclusion of new
haptic devices and peripherals to the system easily as ROS
is language independent middleware and possess the utilities
required for seamless integration.</p>


<!-- <center><h3>Results</h3></center>
<hr class="star-primary">
<p style="text-align: justify"> The results displayed in figures below, depict the average number of steps taken by the robots in order to explore and map the complete maze. It can be observed that the average number of steps reduces exponentially with increase in number of robots. It can also be observed that with increase in number of robots and maze size, the factor of load imbalance comes into picture. While the load imbalance doesn’t represent a particuar trend like Average number of steps, we still can logically deduce that the probability of load imbalance increases with increasing robots. </p>

![image-title-here](/assets/img/ai_result1.png){:class="img-responsive width=176 height=71"}  <br/><br/>

![image-title-here](/assets/img/ai_results2.png){:class="img-responsive width=176 height=71"}  <br/><br/>

 



<center><h3>Conclusion</h3></center>
<hr class="star-primary">

<p style="text-align: justify">We present a problem where a swarm of robots is required to map a maze. We introduce a unique multi-robot approach, which enhances Recursive Backtracking algorithm to the multi-robot case. The average number of steps taken in case of multi robot system as compared to single robot decrease effectively. Another factor of load imbalance i.e. a considerable difference in number of steps taken by individual robots is also observed with increase in size of maze and number of robots. The approach mentioned above, also allowsto map the maze from any starting locations for the robots, thus removing the restriction of starting all robots from a single location in the maze. We hope to scale this maze mapping and shortest path planning algorithm from 2D mazes to 3D mazes that will depict different floors of a multi storey building.</p> -->

<hr class="star-primary">
                            
<ul id ="horizontal-list">
<li class="display: inline">
<strong><a target="_blank"  href="https://github.com/nalinraut/Indoor-Scene-Recognition">Code Repository Link <i class="fa fa-fw fa-github"></i></a>
</strong>
</li>
                                
                                
<li>
<strong><a href="javascript:void(0);">Project-Report</a>
</strong>
</li>
                                
</ul>
     

