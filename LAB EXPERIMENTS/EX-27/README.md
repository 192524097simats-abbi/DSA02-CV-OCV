import cv2
img = cv2.imread("image.jpg")
crop = img[50:200, 50:200]
img[250:400, 250:400] = crop
cv2.imshow("Result", img)
cv2.waitKey(0)
cv2.destroyAllWindows()
