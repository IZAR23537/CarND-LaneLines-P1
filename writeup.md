# **Finding Lane Lines on the Road** 

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

## Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I used the gaussian_blur function to reduce image noise and reduce details. After that, i used the canny function to detect edges then selected the region in the image which contains the two lanes. 
In the end i applied the hough_lines for selecting the required lines and the weighted_img function to make the final blended image.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ignoring the vertical and almost horizontal lines. For the left and right lines selection i used the lines slope values and stored their X and Y values.
For the creation of the left and right lane lines i used the np.polyfit function and stored the slope and intercept values. 
Then with fixed Y positions and calcualed X positions i draw the new lines on the image.

### 2. Identify potential shortcomings with your current pipeline

One potential shortcoming would be when on the selected region there is no lane line and therefore there won't be a drawn line on the image.

Another shortcoming could be that if there are different lane line sizes on the road. The draw lines might not match on the lanes.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ignore the far off detected edge lines.

Another potential improvement could be to draw a fix line when there is no lane line is detected.
