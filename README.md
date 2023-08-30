# Image-Acquisition-from-Web-Cameraa
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import cv2 and capture the video using cv2.VideoCapture(0).
### Step 2:
Write the captured image using cv2.imwrite("imagename",frame).
### Step 3:
Resize the image using cv2.resize(frame, (0,0), fx = 0.5, fy=0.5).
### Step 4:
Display the image until the loop gets over.
### Step 5:
Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180).
## Program:
``` Python
### Developed By:SARGURU K
### Register No:212222230134

## i) Write the frame as JPG file
``` python
import cv2
video = cv2.VideoCapture(0)
while(True):
    t,frame = video.read()
    cv2.imwrite("21222230134_SARGURU.jpg",frame)
    result=False
    if cv2.waitKey(1) == ord('b'):
        break
video.release()
cv2.destroyAllWindows()
```
## ii) Display the video
```
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow('image',frame)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()
```
## iii) Display the video by resizing the window
``` python
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('image', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iv) Rotate and display the video
``` python
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('image', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```
## Output

### i) Write the frame as JPG image
![WhatsApp Image 2023-08-29 at 10 33 11 PM](https://github.com/BaskaranV15/Image-Acquisition-from-Web-Cameraa/assets/118703522/0deb6462-6cc6-4c7c-a688-c3cc5a962e86)
### ii) Display the video
![WhatsApp Image 2023-08-29 at 10 33 11 PM](https://github.com/BaskaranV15/Image-Acquisition-from-Web-Cameraa/assets/118703522/70dc69ff-bd66-43c6-bacc-46543806b93f)
### iii) Display the video by resizing the window
![WhatsApp Image 2023-08-29 at 10 32 47 PM](https://github.com/BaskaranV15/Image-Acquisition-from-Web-Cameraa/assets/118703522/97b3c23c-da59-4835-a0e7-8a527591f869)
### iv) Rotate and display the video
![WhatsApp Image 2023-08-29 at 10 33 25 PM](https://github.com/BaskaranV15/Image-Acquisition-from-Web-Cameraa/assets/118703522/d4972568-18b7-439b-a4ba-cb6f8b9ab3e2)
## Result:
Thus the image is accessed from webcamera and displayed using openCV.
