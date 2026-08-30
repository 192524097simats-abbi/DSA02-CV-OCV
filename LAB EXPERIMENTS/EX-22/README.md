import cv2
import numpy as np
img = cv2.imread("image.jpg")
gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
mask = np.array([[0,-1,0],[-1,5,-1],[0,-1,0]])
sharp = cv2.filter2D(gray, -1, mask)
cv2.imshow("Original", gray)
cv2.imshow("Sharpened", sharp)
cv2.waitKey(0)
cv2.destroyAllWindows()
