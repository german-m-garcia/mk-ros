# ros-makeblock #

ros-makeblock is a do-it-yourself project about creating a mobile robotic platform integrated in the ROS environment. The development starts with Makeblock's [mbot Ranger](https://www.makeblock.com/steam-kits/mbot-ranger), a small educational toy robot powered with an Arduino microcontroller that controls different sensors and actuators. Makeblock makes its code open-source and this makes it easy to extend their robot with more sensing and compute capabilities.


## ROS ##

The [Robot Operating System](https://www.ros.org/) (ROS) is the standard middleware/development environment in the robotics academic community. A ROS environment consists of nodes that communicate with each other to solve specific tasks. For example, one node reads the data coming from a LIDAR sensor and publishes the point cloud information in a standard way for other nodes to interpret it; at the same time, another node might read this point cloud to elaborate a map of the environment.

## Hardware components ##

In the original mBot, a set of AA batteries powers the Arduino microcontroller. We will keep the Arduino, but add a single board computer —[Intel's UpBoard](https://up-board.org/up/specifications)— that communicates with it and with new sensors. Therefore, we replaced the set of AA batteries with a more powerful LiPo battery plus a regulator that supplies adequate voltage and amperage to the microcontroller (e.g. 12V) and the single board computer. This is important: you will need to provide 5V and 4A to the UpBoard.

The following is a list of all the components:

* Makeblock's mBot Ranger: https://www.makeblock.com/steam-kits/mbot-ranger
* Makeblock spare parts:
  * l1: https://www.makeblock.es/productos/placa_i1/
  * 0824: https://www.makeblock.es/productos/viga_0824_48/
  * pack de estructuras: https://www.makeblock.es/productos/mbot_pack_soportes/
  * pack de vigas: https://www.makeblock.es/productos/pack_vigas_0412/

* Intel AAEON UpBoard: https://up-board.org/up/specifications
* Slamtec's RPLIDAR-A1: http://www.slamtec.com/en/lidar/a1
* LiPo battery: FLOUREON RC Akku 2S 7.4V 2200mAh 35C
* Double output regulator: Matek Systems UBEC Duo FPV Dual BEC UBEC 4A 5V - 12V


## Setting up the UpBoard

You can follow this [instructions](https://idorobotics.com/2016/10/31/getting-started-with-the-intel-realsense-robotics-development-kit-rdk/) to set up the operating system (Ubuntu) and the ROS environment on the UpBoard. Once you have a running Ubuntu on the board, you can jump to the next section, to set up the ROS workspace. At the time I started the development I used Ubuntu 16.04.x LTS and ROS Kinetic. This is by now old, but should not be difficult to upgrade the system to work on ROS Noetic on Ubuntu 20.04.

## Workspace setup

$ mkdir ~/ws

$ wstool init src https://raw.githubusercontent.com/german-m-garcia/ros-makeblock/master/rosinstall/.rosinstall?token=ADNOJRYHP6WGMG647A3WFL26RHMRQ

$ catkin init

$ catkin build
