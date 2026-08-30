import cv2
img = cv2.imread("image.jpg")
blur = cv2.GaussianBlur(img, (5,5), 0)
mask = cv2.subtract(img, blur)
k = 2
high_boost = cv2.addWeighted(img, 1, mask, k, 0)
cv2.imshow("Original", img)
cv2.imshow("High Boost", high_boost)
cv2.waitKey(0)
cv2.destroyAllWindows()
