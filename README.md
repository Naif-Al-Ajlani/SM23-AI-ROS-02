# SM23-AI-ROS-02
Download Turtlebot3 with SLAM packeges with compatible ROS packeges to create a map and save it while simultaneously make the robot model determin the environment based on its position.
![183163488-bc7b9d45-897b-4728-9eeb-0e712f8fd050](https://github.com/Naif-Al-Ajlani/SM23-AI-ROS-02/assets/98528261/5a1c8326-727a-4a50-affe-c0ff74b63892)

SLAM stands for "Simultaneous Localization and Mapping", and it is an algorithmic approach used in robotics to solve the problem of building a map of an unknown environment while simultaneously determining the robot's position within that environment.

The basic idea behind SLAM is to use sensor data from the robot's environment, such as laser range finders, cameras, or sonar sensors, to build a map of the environment and at the same time, use this map to estimate the robot's position. This is done by incrementally updating the map and the robot's position based on new sensor data as the robot moves through the environment.

There are several different approaches to implementing SLAM, each with its own advantages and disadvantages. Some of the most common SLAM algorithms include:

Extended Kalman Filter (EKF) SLAM: This is a probabilistic approach that uses an extended Kalman filter to estimate the robot's position and the map of the environment. It is a widely used algorithm for SLAM.

FastSLAM: This is a particle filter-based approach that uses a set of particles to represent the robot's position and the map of the environment. It is particularly well-suited for problems with non-linear dynamics or non-Gaussian sensor noise.

GraphSLAM: This is a graph-based approach that represents the environment as a graph, with nodes representing the robot's position at different times and edges representing the constraints between those positions, such as the distance between two points. It is a popular approach for large-scale SLAM problems.

Occupancy Grid Mapping: This is a grid-based approach that divides the environment into a grid of cells and estimates the probability that each cell is occupied by an obstacle. It is a simple and efficient approach that can handle a large range of sensor data types.

SLAM algorithms are widely used in robotics for applications such as autonomous vehicles, unmanned aerial vehicles, and mobile robots. They are essential for enabling robots to navigate and interact with their environments autonomously.
