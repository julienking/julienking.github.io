---
author: davetcoleman
comments: true
date: 2016-7-21 02:13:26+00:00
layout: page
slug: tutorials
title: Contributing
---

# Contributing to MoveIt!

We want to encourage all MoveIt! users to contribute back to the open source project, whether enhancing documentation, answer user questions, reporting & fixing bugs, reviewing pull requests, or adding new features.

## Enhancing Documentation

Documentation for the MoveIt! project can be found in two places: within the source repositories and on the main website:

### Within the source repositories as Sphinx files

Tutorials and other concepts are documented as [reStructredText](http://docutils.sourceforge.net/rst.html) files (similar to Markdown) in ``doc`` folders in various MoveIt! packages. For example, many of the beginner tutorials use the PR2 robot as an example, and their documentation pages can be found [here](https://github.com/ros-planning/moveit_pr2/tree/indigo-devel/pr2_moveit_tutorials/planning/src/doc)

To edit or add more tutorials, create Github pull requests to the appropriate location and the maintainers will graciously approve your help after review.

If you are interested in generating the html pages locally on your machine, install [rosdoc_lite](http://wiki.ros.org/rosdoc_lite) (``apt-get install ros-kinetic-rosdoc-lite``) and run in the root of the package:

    rosdoc_lite .

i.e. [pr2_moveit_tutorials](https://github.com/ros-planning/moveit_pr2/tree/indigo-devel/pr2_moveit_tutorials). This will automatically pick up the rosdoc.yaml and write the documentation to ``doc/html``

For deploying documentation changes to the web, [Section 3 of rosdoc_lite wiki](http://wiki.ros.org/rosdoc_lite) says that "rosdoc_lite is automatically run for packages in repositories that have rosinstall files listed in the rosdistro repository." This is done about once every 24 hours, [overnight](http://wiki.ros.org/rosdistro/Tutorials/Indexing%20Your%20ROS%20Repository%20for%20Documentation%20Generation).

Note that ``README.md`` files that are popular on Github should be mainly used to redirect users to the corresponding Sphinx files and website pages.

### moveit.ros.org

Once you have created new Sphinx documentation, you'll need to create links to it from the main moveit.ros.org website so that other users can find it. Additionally, some higher level documentation can be found directly on this website, so you'll need to edit it there as well.

To edit or add pages on the MoveIt! website, go to [https://github.com/ros-planning/moveit.ros.org](https://github.com/ros-planning/moveit.ros.org) and either edit inline using Github's web-based editing capability, or ``git clone`` the repo and push pull requests back to the repo.

## Answering User Questions

You can contribute greatly to the MoveIt! community by answer other people's questions on the [MoveIt! mailing list](https://groups.google.com/forum/#!forum/moveit-users)

Additionally, the ROS community asks questions pertaining to MoveIt on [answers.ros.org](http://answers.ros.org/questions/scope:all/sort:activity-desc/tags:moveit/page:1/). Please feel free help answer questions there, and gain Karma in the process!

As an aside, a lot of documentation exists as Q&As on there, and if you feel so compelled, help us move some of that documentation onto the website.

## Reporting & Fixing Bugs

Bugs should be reported to the Github issues page of the appropriate repo. Please leave as much detail as possible including your ROS version, operating system, operating system version, and whether you built from source. Note however that we have limited resources to fix individual bugs, and are more inclined to give advice on helping you fix your own bugs.

### Pull Requests

Our policy for contributing changes to the code base is that no one, not even the maintainers, should commit directly to the repo. Rather, you should create a feature branch on your own fork of the project and create a pull-request when it's ready to be reviewed by someone else. To ease the process of merging yoru requests, please follow your part of the [Guideline for Handling Contributions](pullrequests.markdown).

See [MoveIt! Code Style](code.html) for details on how to format your pull requests.

### Running Tests Locally

You can run MoveIt! tests locally with catkin-tools. To run a test for just 1 package:

    catkin run_tests --no-deps --this -iv

Run test for all packages:

    catkin run_tests -iv

### Using Docker to Review Pull Requests

Docker is very useful for testing pull requests and code changes without breaking your regular development environment. For more information see the [Docker Usage Instructions](/install/docker).

## Adding New Features

We would like to see MoveIt! continue to evolve and so new features are encouraged. However, it can be difficult to ensure that new features do not break existing functionality or user's code. For this reason, we ask you keep your pull requests in the smallest digestible chunks possible - not thousands of lines of changed code.

We recommend you open an issue first asking if the change is a good idea, before implementing it, so that you don't waste your time.

### Unit/Integration Tests

Unit tests and integration tests are **always** welcomed, please add them to your PRs.
