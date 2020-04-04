# **Finding Lane Lines on the Road**


The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of the following steps.
1. Read in the images into a list.
2. Converte the images to grayscale.
3. Do a Gaussian smoothing / blurring.
4. Do a Canny edge detection.
5. Create a masked edges image to define the area for searching for lanes.
6. Do a Hugh space transformation.
7. Draw the identified lines.
8. Combine the line images with the original images.
9. Write the images to files.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by ...

If you'd like to include images to show how the pipeline works, here is how to include an image:

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ...

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
