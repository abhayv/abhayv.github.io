---
layout: default
title: Simulator environments for self driving car research
---

# Simulator environments for self driving car research

In order to experiment with various techniques rapidly, it is useful to have a good simulator environment which is close enough to the real world but flexible enough to do rapid changes. I researched into the various options available:

* (Deep Drive)[http://deepdrive.io/] In this approach, the author has used the game environment for Grand Theft Auto (GTA) as a simulation environment. There are detailed instructions on how to hack the right hooks into the game so that the imagery is available and how to provide the control hooks for moving the simulated vehicle. The advantage of this approach is it provides a fairly realistic simulator since GTA is a pretty sophisticated game. However, the installation is fairly difficult and the setup is custom in the sense that it does not use a standard OS like ROS to build the platform on.

* (Deep Driving)[http://deepdriving.cs.princeton.edu/paper.pdf]. This has been developed by a research group in Princeton where a car racing video game (TORCS)[https://sourceforge.net/projects/torcs/] is used as the simulator. TORCS is an open source car racing platform but is fairly realistic.

* (V-rep)[http://www.coppeliarobotics.com/] offers a great environment for robot simulators. It simulates a range of sensors including a vision sensor on the robot itself which can be used to simulate a self driving car with a front facing camera as  the main visual input. Here is a screenshot of an environment that I have been playing with.

<img class="iborder" src="/assets/vrep.png”/>

* (Gazebo)[http://gazebosim.org/] provides an open source robotics simulator which is deeply integrated with ROS.
