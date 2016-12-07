---
layout: default
title: Abhay Vardhan
---

# Abhay Vardhan

I am a software engineer and an entrepreneur with deep experience in web, data processing, backend systems, and machine learning. I am currently an engineer at Uber where it has been a privilege to work with passionate people solving hard problems which affect millions across the globe.
Previously, I was the co-founder of Blippy, a cool way to discover GIFs and share them with your friends.

I have a PhD in Computer Science from University of Illinois where I worked on using learning techniques for verification of software systems.
After my PhD, I joined Google in the web search team and got hands-on experience in ranking, search evaluation and analysis of large amounts of data.

I am fascinated by the recent advances in Machine Learning, AI and autonomous vehicles. The confluence of large amounts of data, and powerful computing resources is leading a revolution in computers helping us solve problems that were previously considered to be too hard. This has the potential of transforming our society. A good example of this is self driving technology which is disrupting how people move around.

I have been following up on the advances made in deep learning, computer vision, robotics with a particular focus on self driving cars. I have avidly consumed various the AI related classes at [Stanford](http://cs231n.github.io/), [Udacity](https://www.udacity.com/course/self-driving-car-engineer-nanodegree--nd013) and on the web and have been recently working on a project in my spare time to use an Android based toy car and simulation environments to try out various techniques for automation.

If you would like to see a more detailed profile, please visit [my linkedin page](http://www.linkedin.com/in/abhayv). You can also reach me at firstname dot lastname at gmail dot com.

## Posts
{% for post in site.posts %}
<h4><a href="{{ post.url }}">{{ post.title }}</a></h4>
{% unless forloop.last %}
* * *
{% endunless %}
{% endfor %}

