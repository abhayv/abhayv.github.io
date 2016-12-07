---
layout: default
title: Predicting steering angles of a car using front facing camera
---

# Predicting steering angles of a car using front facing camera

I took part in [Udacity's coding challenge](https://medium.com/udacity/challenge-3-image-based-localization-5d9cadcff9e7#.i1hnvb2cv) to predict steering angles of a car using front facing camera. The challenge was partly inspired by [NVIDIA's successful training](https://devblogs.nvidia.com/parallelforall/deep-learning-self-driving-cars/) using a similar approach to use deep learning end to end.

At the outset, the problem is fairly well defined. We are given a sequence of images obtained by the stream coming from the front facing camera and the corresponding steering angle as measured by the sensor. We can build a convolution network similar to VGG or AlexNet to learn the steering angle. My first approach was to apply AlexNet straight up and see what I get.

The initial results were not so good. The loss plateaued after a number of epochs but the model did not do very well on the test data.

The next approach I tried was using a bird eye view transform to try to focus better on potential regions of interest. I realized that the main input to the steering angle is going to be the lanes that the camera sees. So I built a mask over the image that roughly covers where the lanes end up being and blacked out the rest of the image. This had better results.

The other change was to quantize the steering angles into small buckets and use learn the classification instead of trying to predict the exact steering angle as a regression. The reasoning was that there is noise in the steering angle which is probably not useful for learning.

The final code is available on [github](https://github.com/abhayv/self_driving_udacity_challenge2). The model was able to achieve decent results though it was not good enough to make it to the top 5 in the challenge.

