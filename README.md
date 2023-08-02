# SM23-AI-ROS-02
Download Turtlebot3 with SLAM packeges with compatible ROS packeges to create a map and save it while simultaneously make the robot model determin the environment based on its position.

# SLAM defnition

Simultaneous localization and mapping (SLAM) is an algorithmic approach used in robotics to solve the computational problem of constructing or updating a map of an unknown environment while simultaneously keeping track of an agent's(robot) location within that environment.

The basic idea behind SLAM is to use sensor data from the robot's environment, such as laser range finders, cameras, or sonar sensors, to build a map of the environment and at the same time, use this map to estimate the robot's position. This is done by incrementally updating the map and the robot's position based on new sensor data as the robot moves through the environment.

Using a wide range of algorithms, computations, and other sensory data, SLAM software systems allow a robot or other vehicle—like a drone or self-driving car—to plot a course through an unfamiliar environment while simultaneously identifying its own location within that environment.

There are several different approaches to implementing SLAM, each with its own advantages and disadvantages. Some of the most common SLAM algorithms include:

Extended Kalman Filter (EKF) SLAM: This is a probabilistic approach that uses an extended Kalman filter to estimate the robot's position and the map of the environment. It is a widely used algorithm for SLAM.

FastSLAM: This is a particle filter-based approach that uses a set of particles to represent the robot's position and the map of the environment. It is particularly well-suited for problems with non-linear dynamics or non-Gaussian sensor noise.

GraphSLAM: This is a graph-based approach that represents the environment as a graph, with nodes representing the robot's position at different times and edges representing the constraints between those positions, such as the distance between two points. It is a popular approach for large-scale SLAM problems.

Occupancy Grid Mapping: This is a grid-based approach that divides the environment into a grid of cells and estimates the probability that each cell is occupied by an obstacle. It is a simple and efficient approach that can handle a large range of sensor data types.

SLAM algorithms are widely used in robotics for applications such as autonomous vehicles, unmanned aerial vehicles, and mobile robots. They are essential for enabling robots to navigate and interact with their environments autonomously.
![183163488-bc7b9d45-897b-4728-9eeb-0e712f8fd050](https://github.com/Naif-Al-Ajlani/SM23-AI-ROS-02/assets/98528261/5a1c8326-727a-4a50-affe-c0ff74b63892)

# 1- Install-ROS-on-Remote-PC:
After installing ubunto and compatible ROS packges with ubunto virsion downloaded.

Open the terminal and enter below commands in order only one time:-
$ sudo apt update
$ sudo apt upgrade
$ wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_noetic.sh
$ chmod 755 ./install_ros_noetic.sh
$ bash ./install_ros_noetic.sh

# 2- Install-Dependent-ROS-Packages:
This commands is for ROS melodic virsion "change the virsion name if you use deferent virsion than melodic"
$ sudo apt-get install ros-melodic-joy ros-melodic-teleop-twist-joy \
ros-melodic-teleop-twist-keyboard ros-noetic-laser-proc \
ros-melodic-rgbd-launch ros-melodicc-rosserial-arduino \
ros-noetic-rosserial-python ros-noetic-rosserial-client \
ros-noetic-rosserial-msgs ros-noetic-amcl ros-noetic-map-server \
ros-noetic-move-base ros-noetic-urdf ros-noetic-xacro \
ros-noetic-compressed-image-transport ros-noetic-rqt* ros-noetic-rviz \
ros-noetic-gmapping ros-noetic-navigation ros-noetic-interactive-marker

# 3- Install-TurtleBot3-Packages:
Install TurtleBot3 via Debian Packages with compatible ROS virsion ( This commands is for ROS melodic virsion) "change the name if you use deferent virsion than melodic"
$ sudo apt install ros-melodic-dynamixel-sdk
$ sudo apt install ros-melodic-turtlebot3-msgs
$ sudo apt install ros-melodic-turtlebot3

# 4- Gazebo-Simulation:
Install Simulation Packages:
The TurtleBot3 Simulation Package requires turtlebot3 and turtlebot3_msgs packages as prerequisite. Without these prerequisite packages, the Simulation cannot be launched.
Before lucnhing the simulation follow the PC Setup instructions below to install the required packages, if you already did not install required packages and dependent packages

$ cd ~/catkin_ws/src/
$ git clone -b noetic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
$ cd ~/catkin_ws && catkin_make

# 5- Launch Simulation World:
Three simulation environments are prepared for TurtleBot3. Please select one of these environments to launch Gazebo.

"Make sure to completely terminate other Simulation world before launching a new world".
Use the proper keyword among burger , waffle , waffle_pi for the TURTLEBOT3_MODEL parameter before lunching TurtleBot3 world.

TurtleBot3 World lunch

$ export TURTLEBOT3_MODEL=waffle
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch

# 6- Run SLAM Simulation
Open a new terminal from Remote PC and run the SLAM node. Gmapping SLAM method is used by default.
Use the proper keyword among burger , waffle , waffle_pi for the TURTLEBOT3_MODEL parameter when you have lunched the TurtleBot3 World.

$ export TURTLEBOT3_MODEL=waffle
$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping

# 7- Run Teleoperation Node
Open a new terminal from Remote PC and run the teleoperation node from the Remote PC.

Use the proper keyword among burger , waffle , waffle_pi for the TURTLEBOT3_MODEL parameter  when you have lunched the TurtleBot3 World.

$ export TURTLEBOT3_MODEL=waffle
$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch

# 8- Saveing the Map
When the map is created successfully, open a new terminal from Remote PC and save the map. with the follwing command line.
$ rosrun map_server map_saver -f ~/map

# Test
Testing the map with the robot model to determine the environment based on its own position
Note: you can only move the robot from the terminal used in step number seven (Runing Teleoperation Node step)

# resources
1- turtlebot3 quick start guide: https://emanual.robotis.com/docs/en/platform/turtlebot3/quick-start/
2- hector slam: http://wiki.ros.org/hector_slam
3- carto grapher: http://wiki.ros.org/cartographer
4- gmapping: http://wiki.ros.org/gmapping

for more application information check this toutorial:
