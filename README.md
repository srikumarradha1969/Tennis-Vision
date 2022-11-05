![Untitled](https://user-images.githubusercontent.com/43463668/200117490-3496c31f-96de-4f37-839f-24af3d1392b5.png)

**About the Tennis Vision Project**

The detection of white-colored tennis court lines is a standard feature in most tennis-related Apps for coaching or training. In addition, such tennis apps' typical features include tennis ball tracking, player detection, etc. More areas of potential interest would include tennis serve speed measurement and a [Hawk-Eye kind of facility](https://www.topendsports.com/sport/tennis/hawkeye.ht) to determine if the ball is in or out during a serve or rally.

Professional products such as the Hawk-Eye include six or more computer-linked television cameras placed around the court. Hence, it may involve significant costs, probably out of reach for many. Thus, the need for cost-effective options probably feeds from a mobile device's camera on a stand, which can provide some real-time feedback during coaching sessions. 

This Tennis Vision Project has, thus, been inspired by two Github Projects, namely, [**Artlabs** Tennis Tracking](https://github.com/ArtLabss/tennis-tracking) and a [similar Project by **Maxime Bataille** to track tennis players and the ball](https://github.com/MaximeBataille/tennis_tracking), which has been referred to in the Artlabs Project. The main highlight of these projects has been using Tracknet - a deep learning network for tracking high-speed objects. Court Detection is also a separate class or module in the Artlabs Project, written in over 400 lines of code in Python, for which the Hough Transform algorithm has been used to detect the court boundaries as lines.  In the case of Maxime Bataille, cv2.line is drawn between fixed coordinates representing court boundaries and hence, would require videos of matching court size. Also, the court lines have to be visible at all times to complete full runs of the detection.

The current Tennis Vision has attempted to keep the lines of code to a bare minimum so that it can be easily comprehended and improvised later. Also, this approach dictates maximum utilization of existing image processing algorithms, such as thresholding, morphological operations, dilation, and contour detection, so that they can be used rather than created from scratch. Another instance is using cv2.pointPolygonTest to include only centroids of contours of interest. 

Using dilation resulted in thicker lines, which was necessary to ensure the best possible detection of contours in one iteration. Because the tennis court is light or pale blue, its similarity to white made thresholding very sensitive to court color. In other words, for using this project for different tennis videos, some cv2.threshold values may need to be adjusted. 

One distinct feature of this approach has been to use contours, or groups of lines for detection, rather than individual lines, which would make it more appropriate to add a subsequent Hawk-Eye feature of determining whether the ball landed on the court or outside.

