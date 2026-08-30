import cv2
import numpy as np
img = cv2.imread("image.jpg")
matrix = np.float32([[1, 0, 100],[0, 1, 50]])
h, w = img.shape[:2]
translated = cv2.warpAffine(img, matrix, (w, h))
cv2.imshow("Original", img)
cv2.imshow("Translated", translated)
cv2.waitKey(0)
cv2.destroyAllWindows()
