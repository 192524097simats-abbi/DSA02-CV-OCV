import cv2
import numpy as np
cap = cv2.VideoCapture("video.mp4")
src = np.float32([[50,50], [400,50],[50,300], [400,300]])
dst = np.float32([[0,0], [400,0],[0,300], [400,300]])
matrix = cv2.getPerspectiveTransform(src, dst)
while True:
    ret, frame = cap.read()
    if not ret:
      break
    result = cv2.warpPerspective(frame, matrix, (400,300))
    cv2.imshow("Perspective Video", result)
    if cv2.waitKey(30) & 0xFF == ord('q'):
      break
cap.release()
cv2.destroyAllWindows()
