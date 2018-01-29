
Finding Lane Lines on the Road


### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of following steps
1. Convert image to grayscale
2. Apply Gaussian blur to the image
3. Apply Canny edge detection
4. Masking the image so that only the region of interest is processed
5. Apply Hough transform to identify lines
6. Draw the lines on top of the image

In order to draw a single line on the left and right lanes, I modified the draw_lines() function. First I separeted right and left lines points on basis of slope and for data fitting used least squares fitting using function numpy.polyfit() with first degree of fitting polynomial to get the fitting coeficient. And finaly drawn lines on calculated points on basis of coeficient.


### 2. Identify potential shortcomings with your current pipeline
Although Pipeline is working for first 2 videos but there is some fluctuations in line drawing. 

While running for challenge video extrapolated lines are shaking alot and line identification not working as desired, may be because of the curve in road and variation in brightness of road.   


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to try using moving average for smoothing the lines, But not sure how well it will works with sharp curves.

Another potential improvement that I feel that I should try to play with brightness and contrast of image to handle the changing brightness of road.
