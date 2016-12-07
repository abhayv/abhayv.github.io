---
layout: default
title: Image based localization for self driving cars
---

# Image based localization for self driving cars

Localization is an important part of the self driving car technology as one has to know where one is to even begin to do any kind of automation. Traditionally, LIDAR has been used for self driving cars but although it gives detailed sensory data, it is expensive. There has been a move to push the boundaries by using image data alone as cameras are cheap.

I am participating in [Udacity's coding challenge](https://medium.com/udacity/challenge-3-image-based-localization-5d9cadcff9e7#.x4pztnami) to do image based localization. Here, we are given a stream of images from a front facing camera on the car’s dash tagged with the corresponding latitude and longitude from GPS sensors. The task is to be able to match a image presented later and figure out the latitude and longitude by matching to a previously seen image.

Classical SLAM would be too slow for this exercise so I investigated a bunch of different techniques. The main idea is to be able to search efficiently from the previously given images. Here are the some of the approaches I have looked into:

* [Bag of words](http://www.cs.cmu.edu/~16385/lectures/Lecture12.pdf). First, we create a visual vocabulary by extracting feature descriptors from all the images and then cluster them using K-Means. Each cluster then serves as a visual word. Second, we take each image, get the feature descriptor and compute the frequency of the visual words which acts as the representation of the image. We can index the vector representations and then use document retrieval techniques to do efficient search.

* [NetVLAD](http://www.di.ens.fr/willow/research/netvlad/). This approach uses a CNN that is directly trainable end to end to do the localization.

* [FabMap](http://www.roboticsproceedings.org/rss05/p39.pdf). This uses a variation of the bag of words approach and uses probabilistic methods to efficiently search through the previously seen images. 