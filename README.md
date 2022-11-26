# Incampus-navigation-of-Autonomous-vehicles
## Codes are not shared as they are proprietary
The project I have been working on as a part of my Master's thesis is In campus-navigation-of-Autonomous-vehicles. As a part of this project, I worked on the Autonomous shuttle's perception, planning, and control. In perception, I implemented Obstacle detection (Pothole detection). Along with the latter algorithm, other detection algorithms are integrated with the edge computing device NVIDIA AGX Orin, which sits as the computational board on the vehicle. In planning and controlling the vehicle, waypoint navigation was set as an algorithmic part, and MicroAuto Box 3 was set up, which serves as a low-level controller. I was guided by my postdoctorate throughout the process.


## Perception

POTHOLE DETECTION USING DEEP LEARNING
Deep learning is vital in solving perception-based problems in an Autonomous vehicle. Pothole detection is one of such serious problems to be dealt with in the Indian context. Deep learning models such as FRCNN and YOLOv5 are implemented to detect these potholes.
Now working on depth guided Transformer based models too, This model would predict the depth along with detection boxes parallely.

<img src="https://user-images.githubusercontent.com/89637330/200289420-66fcf64d-38d8-4aec-9306-10b764494cd7.png" width="300" height="200" />

Inference done on real time video

## Drive by wire Conversion of Vehicle and Computational device setup

An low levle vontroller (actuator) must be used, which finally sends commands to steer the vehicle, accelerate and brake. Micro Auto box III is
used to serve this purpose. It is a real-time technology that allows for rapid in-vehicle function prototyping. It has a variety of analog or digital I/O
channels, powerful bus and network interfaces, and even a user-programmable FPGA for rapid control loops. Notable expansions, such as a MicroAutoBox III embedded PC for ADAS/AD applications or an I/O module for engine control, are also available. This workflow combines to make the MicroAutoBox III a robust and adaptable development system.
GPU capable edge computing device NVIDIA Jetson AGX ORIN is used as computational device on the vehicle. Initially this board is setup in the lab enabled and tested its capabilities. Now it is handling 5 perception algorithms along with planning and control algorithm. In th initial days NVIDIA Jetson Xavier served as computational board. 

<img src="https://user-images.githubusercontent.com/89637330/200299994-f9552b24-55f9-4ae8-9bfb-625bf141869b.png" width="400" height="200" /> <img src="https://user-images.githubusercontent.com/89637330/200301811-decaf050-f21a-40a7-8fa8-1af65723913e.png" width="400" height="200" /> 


dSpace MicroAutoBox III - Controller and NVIDIA ORIN, NVIDIA AGX Xavier


## Parallel processing over ROS

Perception algorithms and Navigation algorithm are integrated over ROS platform. GNSS, Camera data are passed over ROS which will further direct to all required Algorithms. Collecting back the results from perception algorithms and directing them to Navigation algorithm is done the centralised fashion. All data transfers occur parallely in publisher-subscriber fashion.

<img src="https://user-images.githubusercontent.com/89637330/200306955-0306da85-6485-40da-96b2-8dcd20f055a7.png" width="400" height="200" /> <img src= "https://user-images.githubusercontent.com/89637330/200307257-2a8de613-78c0-4e45-9839-022c9e5909d4.png" width="400" height="200" />

Published ROS topics

## Planning and Control model

Pure Pursuit Algorithm is used to implement the navigation by taking waypoints as reference. The vehicle is localized using the Inertial Navigation System (INS). It gives the present latitude and longitude values of the vehicle; thereby, the distance and heading to the predetermined waypoint is calculated. Steering and acceleration input are calculted which therby reduce the distance and heading errors. Required steering and acceleration are carried on to low level controller and thereby to ECU.

<img src="https://user-images.githubusercontent.com/89637330/200308990-b52affc7-b362-46e2-83da-05e65053b7df.png" width="300" height="150" /> <img src="https://user-images.githubusercontent.com/89637330/200309010-417e7c30-0785-497c-a77f-ce20ea86c1bb.png" width="300" height="150" /> <img src="https://user-images.githubusercontent.com/89637330/200309027-cbf33aab-b467-4dc8-94b7-980180fdbbe9.png" width="300" height="150" />

Shuttle taking a Turn, moving faster on Straight Expressway, halted at a bus stop for Passenger alighting and boarding in Autonomous mode.

## Analysis of Maneuver
<img src="https://user-images.githubusercontent.com/89637330/200312122-1d71e769-31ea-43d4-9584-26b4516c162d.png" width="300" height="150" /> <img src="https://user-images.githubusercontent.com/89637330/200312144-4a93b7dc-d1cb-4f94-98d4-5af1a101d683.png" width="600" height="150" />

Calculated Track error to validate how effective the ego vehicle is moving with respect to the given path.



https://user-images.githubusercontent.com/89637330/201994262-2e89d788-d533-432d-8eac-4a29190beaf7.mp4


