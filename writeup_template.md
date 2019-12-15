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

My pipeline consisted of 5 steps.
1) Converting the images to grayscale
2) Apply Gaussian Smoothing
3) Find the edges by using the canny method
4) Masking out the section of interest in the image
5) Applying the hough transform to the masked out area

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by first identifying the hough lines as either left or right lane markings.  This was accomplished by calculating the slope of each line such that a negative slope indicates a left lane line marking (since the y axis is reversed) and a positive slope is a right lane line marking.  Once the lines were sorted I found the average slope and intercept for both lines, then plugged those back into to the y=mx+b equation to find the the x coordinates (the y coordinates were simply the lowest point in the image and the top of the masked area).  Once the x coordintes were found I could draw out both the right and left lane.

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
