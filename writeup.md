# **Finding Lane Lines on the Road** 

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./test_images/solidWhiteCurve.jpg "Initial Image"

[image2]: ./test_images_output/solidWhiteCurve.jpg "After Lane Lines Detected"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 6 steps. First, I converted the images to grayscale, applied Gaussian Blur to reduce noise and then detected edges using Canny function. I've then applied an image mask defined by a polygon to the edges to keep only the region that consists lane lines and black out other parts of edge detected image. Used Hough Transformation technique to detect line segments in the selected region of edges image.   

Hough transforming the selected region of edges results in multiple line segments but our goal is to draw a single line on the left and right lanes.

Based on the slope, I've grouped the line segments in to two. All line segments with -ve slope belongs to left lane and segments with +ve slope are of right lane. Finding the average slope & intercept of left and right groups gives the parameters to draw a single left and right lanes. I've modified draw_lines() function to include this logic of finding line parameters to draw on image.     

For the resulting images, please see **test_images_output** folder and for video outputs see **test_videos_output**


### 2. Identify potential shortcomings with your current pipeline


One of the potential shortcoming is, this algorithm is not very efficient if road has sharp bends such as in challenge.mp4. I had to use `try` `except` to skip drawing lines on certain frames of challenge video where finding right lane is not acurate.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to use color selection to identify white and yellow lane lines.

Another potential improvement is to be able to handle lane change during which the lane lines may not fall within the region of interest mask.

