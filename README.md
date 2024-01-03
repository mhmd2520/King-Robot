# ROS workspace

## Contents
- [Introduction](/Introduction/SLAM_In_ROS_Introduction.pdf)
- [Prerequisites](#prerequisites)
- [Prerequisites](#prerequisites)
- [Set Up Workspace](#set-up-workspace)
- [king Robot](#king-robot)
- [Control The Robot](#control-the-robot)
- [Autonomous Navigation](/Navigation/Navigation.md)

## SLAM in ROS Introduction

Refer to the PDF file here: [Introduction](/Introduction/SLAM_in_ROS_Introduction.pdf)

## Prerequisites

Replace `<version>` with noetic, melodic etc.
  
- ROS (`$ sudo apt-get install ros-<version>-desktop-full`)
- Xacro (`$ sudo apt-get install ros-<version>-xacro`)
- Gazebo (`$ sudo apt-get install ros-<version>-gazebo-ros`)
- DWA Planner (`$ sudo apt install ros-<version>-dwa-local-planner`)
- GMAPPING (`$ sudo apt install ros-<version>-gmapping`)

## Set Up Workspace
```bash
git clone https://github.com/mhmd2520/king_robot_ws
cd king_robot_ws
catkin_make
source devel/setup.sh
```

## King Robot
Run the world with the Robot
```bash
roslaunch king world.launch
```

<p align="center">
<img src="/media/WorldPicture.png" alt="World Picture"/>
</p>

- Hint: If you want to modify the `world.launch` file to add your own world, make sure to make `<sim_time>0</sim_time>` in the `<YourWorld>.world` file to avoid the following error:
*Spawn service failed. Exiting.*
*[urdf_spawner-6] process has died*

## Control The Robot
Use `teleop_twist_keyboard`

```bash
rosrun teleop_twist_keyboard teleop_twist_keyboard.py cmd_vel:=/king/cmd_vel
```

## Autonomous Navigation

Refer to Autonomous Navigation here: [Navigation](/Navigation/Navigation.md)
