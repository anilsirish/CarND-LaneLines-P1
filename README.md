# CarND-LaneLines-P1
Basic Lane line finding on the road

When we drive, we use our eyes to decide where to go. The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle. Naturally, one of the first things we would like to do in developing a self-driving car is to automatically detect lane lines using an algorithm.

In this project we detect lane lines in images using Python and OpenCV. OpenCV means "Open-Source Computer Vision", which is a package that has many useful tools for analyzing images.

The tools used in this project are region of interest selection, grayscaling, Gaussian smoothing, Canny Edge Detection and Hough Tranform line detection.