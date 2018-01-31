# **Finding Lane Lines on the Road** 

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./output/solidWhiteRight_v2_output.jpg "White line"

[image2]: ./output/whiteCarLaneSwitch_v3.jpg "Yellow line"

[image3]: ./test_videos_output/challenge_output.png "Challenge video"

---

### Reflection

My pipeline consisted of 5 steps. First, I converted the images to grayscale. Second, I blured the image with gaussian blur.Third, I used canny edge detection. Fourth, I limited the work area on the interest portion of the image, in the form of a triangle in front of the camera. Fifth, I used Hough space to find the line of the dots in the image. The result was then drawn back to the original image.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by calculating the slope with the following equation:

slope = (y2 - y1) / (x2 - x1)

and drawing a single line for slope > 0 (representing one lane )and another line otherwise.

In order to draw the lane until the bottom, I calculated the intersection of each of the 2 lines with the hight of the image. That way, I drew the line from the highest point all the way to the bottom.

Here are a couple of the resulting image from the tested images: 

![alt text][image1]

![alt text][image2]

The pipeline also worked great for videos.


One potential shortcoming would be the challenge video. The pipeline was not sharp enough to find the lines for the challenge, getting confused with the curb and the lanes on the other side of the road.

Here is the resulting image:

![alt text][image3]


A possible improvement would be to modify the variables so it would be satisfying for all the provided images and videos.

Another potential improvement could be to go even further and tune the variables to work with other images and videos found online or even recorded by me.
