# Mapping_on_kitti_dataset


![ ](https://github.com/spanthr/Mapping_on_kitti_dataset/blob/main/Images/ezgif.com-gif-maker.gif)

Visualization of Kitti data set with ORB-Slam 


![ ](https://github.com/spanthr/Mapping_on_kitti_dataset/blob/main/Images/ezgif.com-gif-maker%20(1).gif)

Loop closure and Dense Surfel formation in dark

The roboticists are committed to achieve one of the most humbling aspects of bringing intelligence to the robots, so they are efficient as humans with regards to the ability to perceive, orient and process information from the environment. The intelligent robots should be capable of this ability to understand their environment. In Robotics, map building or mapping provides a path towards supporting fully autonomous vehicles for navigation, path planning, decision making and feature detection. 

Introduction: In real life scenario as the robot navigates its environment it must compose a data model or the map of the surroundings using sensors. The sensors and the map generated depends on the application of the robot and its environment. The map is equivalent to what we might consider a picturization or perception of the environment in our mind’s eye.  

This report comprises a step wise explanation of literature survey conducted by the team followed by the procedure and the intricacies involved in the process of successfully generating a map using a novel technique. The tasks included setting up of framework, installing the dependencies, writing the necessary codes and shell scripts and finally generation of maps and its visualization. Due to the time constraints and shortage of resources available the team decided to use just one data set for the procedure. The following sections describe the  

## Motivation 

The motivation behind this mapping is to assist autonomous robots and vehicles in various areas for navigation, motion planning and decision making. This will implement safety and reliability for autonomous driving, localization and mapping system in real time. In addition to this automation can help in the reduction of the number of crashes on the roads. The government data showcases that the 94 percent of the road crashes account for driver behavior or error and there can be significant reduction in the driver errors with the introduction of reliable self-driving vehicles. The highly automated vehicles have the capability to reduce risky and dangerous driver behaviors. The motion planning, Artificial intelligence and controls are only made possible and reliable after we have sufficient information of the environment using appropriate sensors.  

Also, this mapping technique can also be applied for perception of the environment of an autonomous wheelchair. Statistically, its estimated that around 18.5 million Americans are limited to travel in some way. This includes majority of people with disabilities (blind people, people with intellectual development and also wheelchair user, people with epilepsy). The people with disabilities require reliable and affordable transportation for enjoying their civil rights that include opportunities in education, employment, housing, healthcare, housing and participation in community life. There have been several cases of people missing job opportunities and appointment, cases of narrowly avoided catastrophes and long wait for paratransit and impassible sidewalks due to manually operated wheelchairs. Therefore, in order to solve the above problems, the introduction of an autonomous wheelchair is envisioned as the long term of this project. The first part of this detailed study is presented in this report that will resolve the problems related to visual perception, simultaneous map generation and localization of the robot in the environment. This study keeps in mind the environment not only for indoor but also for the outdoor scenario where a wheelchair can operate without any issues. Also, the number of dimensions when increased to a map also increases the computational complexity but this technique can operate on CPU and does not require high end GPU to achieve map generation. 

The most tremendous problem with the SLAM is the correspondence or the data association problem. It refers to whether the sensor measurement recorded at different time correspond to the same physical entity in the real world.  

An additional challenge with robotic mapping is the increasing dimensions to a map that in turn increase the computational complexity. The quantity of the points in a 3D map is potentially much larger than a 2D map.  

Another major challenge is the measurement noise and the control noise in the robot or the vehicle. This means that while the robot is estimating its position with respect to the surrounding using some sensors, the sensor might have errors with the measurement and also the controls that are actuated for example the odometer of the robot can accumulate to have significant effects in the latter stage of mapping. 

The map generated by the robot holds similarity to the way humans draw the map using sensory information, just in robotics scenario it relies completely on external sensors like monocular, depth cameras or LIDAR using a SLAM algorithm. The capabilities of the sensor the map generated could be 2D or 3D. 

The technique satisfies the requirement of generating the map on basis of super pixel-based surfels both runtime and memory efficient.   
 

 

above mentioned tasks in detail. The technique scales different environment with only using CPU computation unlike other techniques that are computationally costly and time consuming and require high end GPU for mapping. The system has the capability to build variety of environment that is from room-scale to urban-scale using the depth information from the RGB-D cameras, stereo camera, or monocular camera. The super pixels extracted from the depth and the intensity images are used to model the surfels in the system. The surfels are organized to pose the graph of the SLAM system to achieve 0 fusion time regardless of the scale of reconstructed models [1]. The fast deformation of the map is done with optimized pose graph in order to fulfill global consistency in real-time. The project aims to conduct comparative study of different mapping techniques and test the performance of the above technique for reconstruction of urban and room-scale using the KITTI dataset. The base code and scripts were cloned from the creator’s repository. 

## INSTALLATION 

The first step related to installing this package is to create a catkin workspace. If ROS is already installed, then this can be achieved by executing the following commands: 

Add this line to your .bashrc file [2]: 

$ source /opt/ros/kinetic/setup.bash 

In a terminal, execute [2]: 

$ mkdir -p ~/catkin_ws/src 

$ cd ~/catkin_ws/ 

$ catkin_make 


Then in the .bashrc, add the following: 

$ source devel/setup.bash 

## DEPENDENCIES 
DenseSurfelMapping/ORB_SLAM2 

Pangolin 

Used for visualization and user interface. 

$ git clone https://github.com/stevenlovegrove/Pangolin 

Installation instruction found in the above link. 

OpenCV 

Used for image manipulation. Installation instructions can be found here. 

Eigen3 

Required by g2o 

DBoW2 and g2o 

Modified to perform place recognition. The g2o library is used for non-linear optimizations. 

ROS 

DenseSurfelMapping/ 

Surfel fusion 

Can be installed in catkin workspace by  

$ catkin_make 

Kitti publisher 

A python wrapper which publishes the KITTI dataset along with pre calculated depth maps using PSMNet. 

Kitti stereo sequence 00 

Download the kitti stereo dataset, sequence 00. 
## Results

![](Images/Picture1.png)

The camera parameters necessary for map generation and transformation of the surfel from local to global.

![](Images/Picture2.png)

The depth threshold 

![](Images/Picture3.png)

The ORB extractor parameters.


![](Images/Picture4.png)

The ORB extractor parameters.

![](Images/Picture5.png)

ORB_SLAM2 map reconstruction. (first loop of the sequence)

![](Images/Picture6.png)



ORB_SLAM2 visualization.

![](Images/Picture7.png)
Kitti Stereo 00 Reconstruction. (Instances before the final loop)


# References
https://www.dropbox.com/s/h9bais2wnw1g9f0/root.pdf?dl=0

[1] Wang, Kaixuan, Gao, Fei, Shen, and Shaojie, “Real-time Scalable Dense Surfel Mapping,” arXiv.org, 10-Sep-2019. [Online]. Available: https://arxiv.org/abs/1909.04250. [Accessed: 02-May-2020].
[2] “Wiki,” ros.org. [Online]. Available: http://wiki.ros.org/catkin/Tutorials/create_a_workspace. [Accessed: 02-May-2020].
[3] HKUST-Aerial-Robotics, “HKUST-Aerial-Robotics/DenseSurfelMapping,” GitHub, 12-May-2019. [Online]. Available: https://github.com/HKUST-Aerial-Robotics/DenseSurfelMapping/tree/master/ORB_SLAM2. [Accessed: 02-May-2020].
[4] Multi-Level Surface Maps for Outdoor Terrain Mapping and Loop Closing - IEEE Conference Publication. [Online]. Available: https://ieeexplore.ieee.org/document/4058725. [Accessed: 02-May-2020].
[5] Probabilistic Terrain Mapping for Mobile Robots With Uncertain Localization - IEEE Journals & Magazine. [Online]. Available: https://ieeexplore.ieee.org/document/8392399. [Accessed: 02-May-2020].


# License
License
Copyright (C) 2020 Shaurya Panthri.

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program. If not, see http://www.gnu.org/licenses/
