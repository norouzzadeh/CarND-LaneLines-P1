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

[image1]: ./test_images_output/solidWhiteCurve.jpg "Test image"

---

### Reflection

### 1. Pipeline:

The pipeline developed here, consists of 7 steps. At first, some preprocessing are applied to the input image. The image is converted to the grayscale and then a Gaussian blur filter with kernel size = 5 is applied to the grayscale image. In the next step, the Canny edge detection algorithm is performed. By some tuning, the low and high thresholds are selected as 150 and 300 respectively. In the 3rth step, a region of interest is selected to remove boundaries and make the lane line detection process simpler. The Hough lines transform is applied to the image in the next step, in order to find straight lines from detected edges. The detected lines are lied on either left or right lane lines. It is assumed that the left and right lane lines are located on the left and right half of the image. Iterating through detected lines, it is determined that each line is located in the left or right half of the image. The start and end points of each hough line is fed into a robust RANSAC estimator in order to find the final lane line. Finally, the detected lane line is extended to cover most of the lower half the input image.

In order to draw a single line on the left and right lanes, the perform_RANSAC() function is designed such that it finds the corresponding x coordinate for the maximum and minimum value of y. It is assumed that the maximum value is equal to the image height and its minimum is higher than the half the image height by a constant margin. Therefore, the lane line is drawn from bottom of the image to somewhere not reaching the lower half of the image. 

Here's an example of the achieved results on a single image.

![alt text][image1]


### 2. Potential shortcomings


One potential shortcoming would be what would happen when the lane line is occluded by shadows or light conditions change rapidly. 

Another shortcoming could be objects on the boundaries having similar shape or color to the lane line.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to perform a probabilistic reasoning about the slope and location of each lane line.

Another potential improvement could be to use context information such as the distance between to lane lines in order to perform sanity checking.
