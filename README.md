![Untitled](https://user-images.githubusercontent.com/43463668/200117490-3496c31f-96de-4f37-839f-24af3d1392b5.png)

**About the Tennis Vision Project**

The detection of white-colored tennis court lines is a standard feature in most tennis-related Apps for coaching or training. Other typical features include tennis ball tracking, player detection, etc. Further, there is speed measurement of the tennis serve and a [Hawk-Eye kind of facility](https://www.hawkeyeinnovations.com/track) to determine if the ball is in or out during a serve or rally.

Professional products such as the Hawk-Eye include six or more computer-linked television cameras placed around the court. Hence, given its significant costs, cost-effective options will be needed, such as video from a mobile device's camera kept on a stand, which can provide some real-time feedback during coaching sessions. 

This Tennis Vision Project has, thus, been inspired by two Github Projects, namely, [**Artlabs** Tennis Tracking](https://github.com/ArtLabss/tennis-tracking) and a [similar Project by **Maxime Bataille** to track tennis players and the ball](https://github.com/MaximeBataille/tennis_tracking), which has been referred to in the Artlabs Project. The main highlight of these projects has been using Tracknet - a deep learning network for tracking high-speed objects. Court Detection is also a separate class or module in the Artlabs Project, written in over 400 lines of code in Python, for which the Hough Transform algorithm detects court boundaries as lines.  In the case of Maxime Bataille, cv2.line is drawn between fixed coordinates representing court boundaries and hence, would require videos of matching court size. Also, the court lines have to be visible at all times to complete full runs of the detection.

Here, the basic approach is to use contours, or groups of lines for detection, rather than individual lines, which would later facilitate adding a Hawk-Eye kind of feature for determining whether the ball landed on the court or outside.

The lines of code are kept to a bare minimum so that they can be easily comprehended and improvised later. Also, existing image processing algorithms for thresholding, morphological operations, dilation, and contour detection, are utilized so that code need not be created from scratch. Here, the cv2.pointPolygonTest filters out centroids of contours drawn on the tennis court lines, eliminating contours outside, such as the Umpire's chair, etc. 

Because the tennis court is light or pale blue, its similarity to white made thresholding very sensitive to court color. In other words, for using this project for different tennis videos, some cv2.threshold values may need to be adjusted. Using dilation results in thicker lines, which is necessary for the best possible detection of contours in one iteration; else, the contours break into smaller lengths, making it difficult to merge into single large contours. 

