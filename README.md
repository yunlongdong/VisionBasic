# Vision Basic

### Perspective Transformation

[perspective transformation tutorial](https://pysource.com/2018/02/14/perspective-transformation-opencv-3-4-with-python-3-tutorial-13/)
code in ```src```


```python
import numpy as np
import cv2
 
frame = cv2.imread('fig.jpg')
 
 
cv2.circle(frame, (155, 120), 5, (0, 0, 255), -1)
cv2.circle(frame, (480, 120), 5, (0, 0, 255), -1)
cv2.circle(frame, (20, 475), 5, (0, 0, 255), -1)
cv2.circle(frame, (620, 475), 5, (0, 0, 255), -1)

pts1 = np.float32([[155, 120], [480, 120], [20, 475], [620, 475]])
pts2 = np.float32([[0, 0], [500, 0], [0, 600], [500, 600]])
matrix = cv2.getPerspectiveTransform(pts1, pts2)

result = cv2.warpPerspective(frame, matrix, (500, 600))

cv2.imshow("Frame", frame)
cv2.imshow("Perspective transformation", result)

cv2.waitKey(0)
```
![](https://raw.githubusercontent.com/yunlongdong/VisionBasic/master/src/pers_fig.jpg)
