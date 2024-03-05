# mk-ros #

[mk-ros](https://german-m-garcia.gitbook.io/mk-ros/) is a do-it-yourself project about creating a mobile robotic platform integrated in the ROS environment. The development starts with Makeblock's [mbot Ranger](https://www.makeblock.com/steam-kits/mbot-ranger), a small educational toy robot powered with an Arduino microcontroller that controls different sensors and actuators. Makeblock makes its code open-source and this makes it easy to extend their robot with more sensing and compute capabilities.
More details of the project can be found on [gitbook](https://german-m-garcia.gitbook.io/mk-ros/).


## ROS ##

The [Robot Operating System](https://www.ros.org/) (ROS) is the standard middleware/development environment in the robotics academic community. A ROS environment consists of nodes that communicate with each other to solve specific tasks. For example, one node reads the data coming from a LIDAR sensor and publishes the point cloud information in a standard way for other nodes to interpret it; at the same time, another node might read this point cloud to elaborate a map of the environment.


## Setting up the UpBoard

You can follow this [instructions](https://idorobotics.com/2016/10/31/getting-started-with-the-intel-realsense-robotics-development-kit-rdk/) to set up the operating system (Ubuntu) and the ROS environment on the UpBoard. Once you have a running Ubuntu on the board, you can jump to the next section, to set up the ROS workspace. At the time I started the development I used Ubuntu 16.04.x LTS and ROS Kinetic. This is by now old, but should not be difficult to upgrade the system to work on ROS Noetic on Ubuntu 20.04.

## Workspace setup

Check out this project to some local directory, e.g. ~/ros-makeblock, in order to use the .rosinstall file to set up the ROS workspace:

$ mkdir ~/ws

$ wstool init src  ~/ros-makeblock/rosinstall/.rosinstall 

$ catkin init

$ catkin build
