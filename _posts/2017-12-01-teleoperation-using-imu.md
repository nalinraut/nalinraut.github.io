---
layout: projects
title:  "Robot Teleoperation by Inertial Measurement Unit"
duration:   "November 2017 - December 2017"
excerpt: "Foundation of Robotics"
project: true
---
![image-title-here](/assets/img/imu.gif){:class="img-responsive width=176 height=71"} 

<center><h3>Description</h3></center>
<hr class="star-primary">
<p style="text-align: justify">Human safety has always been an issue in hazardous environmental working in any field. To overcome these problems of human safety robot technology can be proved to be a boon. Teleoperation can be a very good way to operate robots from a distance and at the same time keeping the human operator in a safe distant environment. Hence, the most basic way to do this is using an IMU Inertial Measurement Unit, which gives us 9 degrees of freedom. So the flexibility of this particular sensor enables us to operate a robot easily. Our project involves a robot in simulation, which is a 4 degree  freedom arm that is operated by the IMU sensor using an arduino board as our controller. We use the gazebo simulator for our simulation and also the Robot Operating System (ROS) for the communication between the IMU sensor and the robot. The robot uses the IMU signals to move its arm and push an object off the table.</p>


<h3>Methodology</h3>
<hr class="star-primary">
<p style="text-align: justify">
* At first, the arduino collects the sensor data from IMU sensor.<br/>
* Now, the arduino sketch(c++ code) running on arduino board publish the sensor data in form of a geometry_msg (imu_msg) to the ROS Topic (/team7/imu_data)<br/>
* The python program (pub_to_arm.py) subscribes to the topic “/team7/imu_data”, processes the data and create a message to publish to the ROS Topic/rrbot/joint1_position_controller/command.<br/>
* Over the ROS controller package, this message simulates the robot arm movement in Gazebo.<br/>
</p>


![image-title-here](/assets/img/RBE500_methodology.png){:class="img-responsive width=176 height=71"} 


<hr class="star-primary">
                            
<ul class="list-inline item-details">
                                
    <li>
        <strong><a target="_blank"  href="https://github.com/nalinraut/Indoor-Scene-Recognition">Code Repository Link <i class="fa fa-fw fa-github"></i></a>
        </strong>
    </li>
                                
</ul>
