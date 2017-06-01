# **Finding Lane Lines on the Road** 

## Project one of Udacity CarND Program

### Alireza Norouzzadeh

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Preprocess the input image.
* Find Canny edges.
* Apply a region-of-interest selection.
* Find Hough lines.
* Separate lines into left and right segments.
* Performa RANSAC estimation on each segment to find left and right lane lines.
* Draw both left and right lane lines on the input image.


[//]: # (Image References)

[image1]: ./test_images/solidWhiteCurve.jpg "Test image"

---

### Reflection

### 1. Pipeline:

The pipeline developed here, consists of 7 steps. At first, some preprocessing are applied to the input image. The image is converted to the grayscale

and then a Gaussian blur filter with kernel size = 5 is applied to the grayscale image.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I .... 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
