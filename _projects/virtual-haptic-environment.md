---
title: "Virtual Haptic Environment"
excerpt: "Robot Dynamics - January 2018 - May 2018"
collection: projects
---

![Virtual Haptic Environment]({{ '/assets/img/dyn.gif' | relative_url }}){:style="max-width: 500px; height: auto;"}

## Description

With the advancement of technology, robot assisted surgical systems are developed to overcome the limitations of pre-existing minimally-invasive surgical procedures. However, these surgical systems lack real time force feedback during the operation. Haptics and force feedback allow a surgeon to make more controlled movements in simulation and reality, but so far neither has been extensively implemented. This paper aimed to model a virtual gripper to interact with dynamic bodies present in the environment and calculate simulated tip forces to transfer back to the haptic device and subsequently the user. The force feedback produced at the gripper is translated to the haptic device, enabling the user to feel the forces generated at the gripper. The simulated environment, dynamical calculations, and feedback were tested using the haptic device controlling the modelled gripper by holding, moving, and acting upon bodies present in the virtual environment.

## Methodology

The idea of virtual haptic environment for surgical simulation has been realized through the integration of several open source softwares, the most crucial of them being CHAI3D, ROS, OpenGL, and Bullet Physics engine. Chai3D is the most effective haptic research software which has been integrated with ROS to establish communication between the virtual haptic environment and the physical haptic devices like da vinci, Geomagic Touch and Novint Falcon. The CHAI3D library internally uses OpenGL and Bullet physics engine to model the computer graphics and simulate the physics respectively. A high level OpenGL wrapper library called GLFW has been used to develop the modules and virtual environments as it allows easy usage of the rather complex OpenGL library. The Bullet physics engine was used to model the physical interactions between the objects for example in the pick and place module discussed in the section IV-C.

The CHAI3D library automatically identifies the haptic devices connected to the computer and spawns the tool in the virtual environment which is set while developing the module. Specifically for the MTM(master tool manipulator) of DVRK, the tool that represents the haptic device in the environment is a gripper as shown in Fig. 6. This gripper mimics the MTM and can be opened and closed by pinching action performed on the MTM. The haptic tool used for the Geomagic touch device for the purpose of incision practice is a knife or a thin surgical tool as mentioned in section IV-B as the manipulator of Geomagic touch is a stylus having 6 Degrees of Freedom.

For establishing the communication between Novint Falcon and CHAI-ROS bridge, ros-falcon Catkin package was installed along with the device drivers. Although CHAI3D detects to Novint Falcon automatically, this ROS package allows the Falcon to interact with the virtual DVRK as the DVRK library has been developed as a ROS package. This package allowed the easy manipulability of gripper using the Falcon device while receiving accurate haptic feedback. The pick and place module discussed in section IV-C relies upon the falcon device with the modified gripper design.

Using the Geomagic touch device with CHAI3D is a challenge as the device is old and not supported directly by the CHAI3D library. Although there exists procedures to install the device kernels for the CHAI environment to detect it, we were unsuccessful in doing so because of operating system compatibility issues. Also, the native kernel would not provide ROS interfacing. To tackle this situation, the Geomagic ROS package was installed and a teleoperation module was developed from scratch to interface the Geomagic touch with the virtual MTML device in the haptic simulation. The Geomagic ROS package provides the ROS topics for pose, force and twist that were used to establish its communication with the MTML as the DVRK ROS package provides similar ROS topics. This module aided us in realizing the incision practice task as discussed in section IV-B.

**Code Repository:** [GitHub](https://github.com/nalinraut/daVinci_haptics)

