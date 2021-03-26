# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.


My pipeline consisted of 8 steps. 
1-Convert the images to grayscale, then I get a darker version of them.
2-Extract a mask for white and yellow using real images converted to HSL color space where white and yellow better represented.
3-Apply the mask to darkend grayscale images to get masked image in this way i can see white and yellow.
4-Smooth suche masked images with gaussian to reduce noise and reduce details.
5 Apply Canny Edge Detector to Gaussian blurred images 
6-Get images with region of interest.
7-Hough Transform Line Detection.
8-Average multiple lines into single one and extrapolate to connect diconnected once .

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when there are curved lines  

Another shortcoming could be different road conditions


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to apply kalaman filter to predect lanes
Another potential improvement could be to adopt feature-based method for road boundary detection in both straight and curved lane lines. The Sobel edge detection is performed followed by Inverse Perspective Mapping (IPM) to extract feature points from left and right lane markings. The polynomial regression is then applied to approximate both lane lines from two datasets of points. Finally, the slopes of both lines are exploited for identifying the direction of road lane. 
