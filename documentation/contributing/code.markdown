---
author: davetcoleman
comments: true
date: 2016-8-1 02:13:26+00:00
layout: page
slug: code
title: Style Guidelines
---

# MoveIt! Code Style Guidelines

We use the [ROS C++ Style guide](http://wiki.ros.org/CppStyleGuide) for all C++ development and the [ROS Python Style guide](http://wiki.ros.org/PyStyleGuide) for Python.

To ease your development, we recommend the automated code formatter ``clang-format`` with a ROS configuration found [here](https://github.com/davetcoleman/roscpp_code_format)

In addition MoveIt! has some extra style preferences:

## C++

 - As of ROS Kinetic we use C++11
 - Use the C++ standard library (``std::``) whenever possible
 - Avoid C-style functions such as ``FLT_EPSILON`` - instead use ``std::numeric_limits<double>::epsilon()``
 - Boost is an encouraged library when functionality is not available in the standard library
 - Prefer full variable names over short acryonms - e.g. ``robot_state_`` over ``rs_``
 - Deprecate functions using MOVEIT_DEPRECATED in [deprecation.h](https://github.com/ros-planning/moveit/blob/kinetic-devel/macros/moveit_core/include/moveit/macros/deprecation.h)

## ROS

 - The ROS logging functionality is utilized and namespacing your logs are recommended, i.e. ``ROS_INFO_NAMED("planning_scene", "Starting listener")``

## MoveIt-Specific

 - For creating ``shared_ptr`` of any object, use MoveIt!'s standard [macro](https://github.com/ros-planning/moveit/blob/kinetic-devel/moveit_core/macros/include/moveit/macros/class_forward.h) ``MOVEIT_CLASS_FORWARD(ClassName)`` before the class declaration, and add the include ``#include <moveit/macros/class_forward.h>``. This will create two typedefs of shared pointers - ``<ClassName>Ptr`` and ``<ClassName>ConstPtr`` using either ``boost`` or ``std``.
