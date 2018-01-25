# **Project Report: Finding Lane Lines on the Road** 

## Finding lane lines on the road

For this project, a set of tools were used to identify lane lines. It consists on 5 steps:

### 1. Color Selection

First, used RGB color space to identify white and yellow lines, then converted the images into grayscale and applied some smoothing to make edges clearer.

### 2. Canny Edge Detection

After smoothing the edges, applied the Canny edge detector algorithm in order to find straight lines used especially for lane lines.

### 3. Region of interest selection

After identifying the lines, in order to remove the noise by a region were lines look longer using polygon of four sides which i called region of interest.

### 4. Hough Transform Line detection

Then used Hough Line Transform Algorithm to extract the lines in our region of interest. The i used the draw_lines function with a small change (no longer changes the original images) to draw the lines in the images. 

### 5. Average or extrapolate lane lines and draw in images

To able extrapolate lane lines, started by finding the average slope and intercept, then converted those lines into pixel points as per cv2.line requirements. Created draw_lane_lines function that draws extrapolated lines. This happens to be the main function to draw the lines.


## Conclusion

The pipeline presented is fairly successful, the videos generated show clearly identified lane lines with a fair accuracy.

This pipeline only works well for straight lane lines. The lanes near the car are mostly straight. It is bad for steep roads as we use center of image to create our region of interest mask.

A possible improvement would be to to detect the horizontal line (between the sky and the earth) so that we can tell up to where the lines should extend.	

