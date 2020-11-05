---
layout: install
slug: source_install_moveit2
title: MoveIt 2 Source Build - Linux
---
{% include install-feedback.html %}

# MoveIt 2 Source Build - Linux

Installing MoveIt 2 from source is the first step in contributing new features, optimizations, and bug fixes back to the open source project. Thanks for getting involved!

<img class="docker-img" src="/assets/install_page/docker-illustration.png"/>

MoveIt is mainly supported on Linux, and the following build instructions support in particular:

- Ubuntu 20.04 / ROS 2 Foxy Fitzroy

In the future, we would like to expand our source build instructions to more OS's, please contribute instruction write-ups to [this repo](https://github.com/ros-planning/moveit.ros.org).

These instructions assume you are running on Ubuntu 20.04.

## Prerequisites

### Install <img src="/assets/install_page/ros_logo.jpeg"/>

[Install ROS2 Foxy](https://index.ros.org/doc/ros2/Installation/Foxy/Linux-Install-Debians/) following the installation instructions. Use the desktop installation and don't forget to source the setup script.

[Install ROS2 Build Tools](https://index.ros.org/doc/ros2/Installation/Foxy/Linux-Development-Setup/#install-development-tools-and-ros-tools) up until setting up rosdep (we're using slightly different steps for setting up our workspace)

### Create Workspace and Source

Create a colcon workspace:

    export COLCON_WS=~/ws_ros2/
    mkdir -p $COLCON_WS/src
    cd $COLCON_WS/src

## Download Source Code

Download the repository and install any dependencies:

    wget https://raw.githubusercontent.com/ros-planning/moveit2/main/moveit2.repos
    vcs import < moveit2.repos
    rosdep install -r --from-paths . --ignore-src --rosdistro foxy -y

## Build MoveIt

Configure and build the workspace:

    cd $COLCON_WS
    colcon build --event-handlers desktop_notification- status- --cmake-args -DCMAKE_BUILD_TYPE=Release

### Source the Colcon Workspace

Setup your environment - you can do this every time you work with this particular source install of the code, or you can add this to your ``.bashrc`` (recommended):

    source $COLCON_WS/install/setup.bash

### Quick Start

We've prepared a simple demo setup that you can use for quickly spinning up a simulated robot environment with MoveItCpp.

<a href="https://github.com/ros-planning/moveit2/tree/main/moveit_demo_nodes/run_moveit_cpp" target="_blank">
  <span class="link-with-background">
    MoveItCpp Demo Package
  </span>
</a>
