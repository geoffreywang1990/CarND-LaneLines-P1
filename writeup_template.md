# **Finding Lane Lines on the Road** 

## Yujun Wang

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. 

* Bonvert the images to grayscale
* Blur the grayscale image with gaussian filter
* Detect edge using canny edge detector
* Seletct a ROI of potentional road marks could appear in the image 
* Detect straight lines within the ROI with hough transform line detector
* Select lines with a slope between 0.876058051 and 2.44685437779 rad
* Draw those lines on top of the original image

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by selecting lines with a slope between 0.876058051 and 2.44685437779 rad


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when 
* it's a curving line
* line marks are not good
* low light condition

Another shortcoming could be 
* hough transform is too slow


### 3. Suggest possible improvements to your pipeline

A possible improvement would be: insteaded of using hough transform to find straight lines, use find countour function to get the boundry of those marks, and fit a line to it, it will be faster than hough transform.


