---
author: admin
comments: false
date: 2016-8-5 20:43:44+00:00
layout: page
slug: install
title: Install
---

> MoveIt! is currently developed against **Ubuntu and ROS Indigo and Jade**. **ROS Kinetic** is not yet released. It is recommended that you move to ROS Jade for the latest features.

**Developers:**: see [source install](source_install.html) instructions.

# Binary Installation Instructions

MoveIt! is released every month or so into Ubuntu Debians via the ROS infrastructure. For more information see the [target platforms](http://www.ros.org/reps/rep-0003.html)

## Prerequisite: Install ROS

Follow all the instructions to install the base version of ROS: [Install ROS-Base](http://wiki.ros.org/indigo/Installation/Ubuntu). Please make sure you have followed all the ROS installation steps, including calls to rosdep.

Choose your ROS distribution below:

* * *

## ROS Indigo

*Note for Ubuntu 13.4 32 bit users*: There is a bug with GCC 4.7 on Ubuntu 13.4 32bit with Eigen 3.1.2. It's not likely to be fixed, so upgrade/downgrade your system to 13.4 64 bit resp. 12.4.

### Ubuntu Installation: Debian Packages for MoveIt!

Simply run:

    sudo apt-get install ros-indigo-moveit-full

### Optional: Install PR2 Debian Packages for MoveIt!

    sudo apt-get install ros-indigo-moveit-full-pr2

### Setup your environment

    source /opt/ros/indigo/setup.bash

See bottom of page for quick start

* * *

## ROS Jade

Partial support for Jade is currently available, see [Github Issue](https://github.com/ros-planning/moveit/issues/22)

### Ubuntu Installation: Debian Packages for MoveIt!

Simply run:

    sudo apt-get install ros-jade-moveit-*

*Note*: the meta package ``moveit-full`` is not yet available but will be replaced with the new metapackage ``moveit``

### Setup your environment

    source /opt/ros/jade/setup.bash

See bottom of page for quick start

* * *

## ROS Kinetic

MoveIt! for Kinetic is not yet released, see [Github Issue](https://github.com/ros-planning/moveit/issues/18)

* * *

## Previous ROS Versions

See [Source Installation Instructions for unsupported versions of MoveIt!](deprecated)

* * *

## Quick Start

Try planning in Rviz with the PR2 move_group demo: [MoveIt! Rviz Plugin Tutorial](http://docs.ros.org/indigo/api/moveit_ros_visualization/html/doc/tutorial.html)
