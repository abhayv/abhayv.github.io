---
layout: default
title: Android based toy self driving car
---

# Android based toy self driving car

I am working on building a toy car for trying out various automation techniques for self driving cars. While not the real deal, this lets me play with lane detection, object detection, localization, path planning, sensor fusion and control techniques.

I started with the assumption that Android would be a good platform to experiment upon as most modern phones have a reasonably fast processor, plenty of memory and a range of sensor including camera, accelerometer, and GPS. The electric motor and the associated board can be completely dumb, just taking commands from the Android device which uses all the sensors to do perception, prediction and path planning.

Here are all the parts I used:

* [SparkFun Redbot Basic Kit](https://www.sparkfun.com/products/13166). This has DC motors, chassis, an Arduino UNO board with motor controller and some basic sensors. (About $85)
* Any modern Android smart phone (Reuse some phone that you have, otherwise runs for $300)
* USB mini cable to connect the redbot to the computer ($6)
* USB mini to micro cable to connect the redbot to the Android phone ($6)

<img class="iborder" src="/assets/android_car.jpg"/>

I use [ROS](http://www.ros.org/) as the base OS to manage all the devices. Here is a block diagram showing the various nodes. The Android phone has a camera which publishes a stream of images. The Arduino is hooked up to the Android phone via the USB cable which connects using serial data. I use rosserial to allow the Android phone to proxy an ROS node on Arduino’s behalf. Finally, there is a control node which observes all the input data and issues the right commands to make the robot move.

<img class="iborder" src="/assets/android_schematic.jpg"/>


