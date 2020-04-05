# **Finding Lane Lines on the Road**


The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

[image1]: ./test_images_output/solidWhiteCurve.jpg "solidWhiteCurve"
[image2]: ./test_images_output/solidWhiteRight.mp4.png "solidWhiteRight.mp4"
[image3]: ./test_images_output/solidYellowLeft.mp4.png "solidYellowLeft.mp4"

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

In order to draw a single line on the left and right lanes, I modified the draw_lines() function with the following thoughts.
1. Separate the lines to left and right ones.
2. Find the longest line segment among the left or right lines.
3. Extrapolate this longest line segment to the top and bottom of the region of interest.

From the output test images I can see, this function works well, for example:

Note: Since I used `cv2.imshow`, the color [255, 0, 0] in drawing_lines is blue.

![solidWhiteCurve][image1]

In the videos, this function delivers also good results, from each frame point of view.

Screenshot from solidWhiteRight.mp4:

![solidWhiteRight.mp4][image2]

Screenshot from solidYellowLeft.mp4:

![solidYellowLeft.mp4][image3]

### 2. Identify potential shortcomings with your current pipeline

1. The region of interest is predefined in the code. Although I referred to the image shape, not absolute values, but this region would only work for this kind of images and videos (540 x 960, lanes in the lower half). For a certain car model, the lane cameras would deliver the same kind of images and videos, so this code could work, but possibly not for another car model， for example challenge.mp4, where the camera is mounted probably behind the wind screen, and the images have the engine hood in them, causing trouble for lane detection.

2. When I play the videos, I can see the lines are not as stable as in P1_example.mp4. They jump back and forth within small distances. I am not sure if this will have impact on other autonomous driving functions, which depend on the identified lanes.

3. The challenge.mp4 is indeed challenging, because on the left side, there is this low wall with shadows; there are color changes between road segments; the outline of the engine hood is in the images; all these could be identified as lanes.


### 3. Suggest possible improvements to your pipeline

The following points are numbered corresponding to the points under shortcomings.

1. A possible solution would be to calibrate the region of interest for each car model.

2. A potential improvement could be to use the longest two or three line segments to calculate their average position and slope, instead of only one line segment.

3. I looked at the reasonable range of line slopes and added this range to draw_lines. It worked so far as the disturbing factors were no longer identified as lanes. But there are frames with no identified left or right lanes. A possible improvement could be to adjust the Canny and Hugh parameters to this video / this car model.
