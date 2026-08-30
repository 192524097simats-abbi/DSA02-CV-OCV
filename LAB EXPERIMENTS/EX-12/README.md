import cv2
import numpy as np
img = cv2.imread("image.jpg")
src = np.float32([[50,50], [300,50],[50,300], [300,300]])
dst = np.float32([[0,0], [300,0],[0,300], [300,300]])
matrix = cv2.getPerspectiveTransform(src, dst)
result = cv2.warpPerspective(img, matrix, (300,300))
cv2.imshow("Perspective", result)
cv2.waitKey(0)
cv2.destroyAllWindows()
