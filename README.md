# Image-Acquisition-from-Web-Camera
## Aim

To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7

## Algorithm
## Step 1:
Import cv2 and capture the video using cv2.VideoCapture(0).

## Step 2:
Write the captured image using cv2.imwrite("NewPicture.jpg",frame).

## Step 3:
Resize the image using cv2.resize(frame, (0,0), fx = 0.5, fy=0.5).

## Step 4:
Display the image until the loop gets over.

## Step 5:
Rotate the image using cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180).



## Program:
### Developed By: Janani.R
### Register No:21222120039

i) Write the frame as JPG file
```
import cv2
img = cv2.VideoCapture(0)
while(True):
    imagee,frame = img.read()
    cv2.imshow('myimage',frame)
    if cv2.waitKey(1) == ord('c'):
        break
img.release()
cv2.destroyAllWindows()
```

ii) Display the video
```
import cv2
video = cv2.VideoCapture(0)
while (True):
    cap,frame=video.read()
    cv2.imshow('Capturing Video',frame)
    if cv2.waitKey(1) == ord('q'):
        break
video.release()
```

iii) Display the video by resizing the window
```
import cv2
import numpy as np
img  = cv2.VideoCapture(0)
while True:
    pic,frame = img.read()
    width = int(img.get(3))
    height = int(img.get(4))
    image = np.zeros(frame.shape, np.uint8)
    small_frame = cv2.resize(frame,(0,0),fx =0.5, fy = 0.5)
    image[:height//2, :width//2]=small_frame
    image[height//2:, :width//2]=small_frame
    image[:height//2, width//2:]=small_frame
    image[height//2:, width//2:]=small_frame
    cv2.imshow('myimage',image)
    if cv2.waitKey(1) == ord('c'):
        break
img.release()
cv2.destroyAllWindows()
```

iv) Rotate and display the video
```
import cv2
import numpy as np
img  = cv2.VideoCapture(0)
while True:
    pic,frame = img.read()
    width = int(img.get(3))
    height = int(img.get(4))
    image = np.zeros(frame.shape, np.uint8)
    small_frame = cv2.resize(frame,(0,0),fx =0.5, fy = 0.5)
    image[:height//2, :width//2]=cv2.rotate(small_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=small_frame
    image[:height//2, width//2:]=small_frame
    image[height//2:, width//2:]=cv2.rotate(small_frame,cv2.ROTATE_180)
    cv2.imshow('myimage',image)
    if cv2.waitKey(1) == ord('c'):
        break
img.release()
cv2.destroyAllWindows()
```

## Output

### i) Write the frame as JPG image

![WhatsApp Image 2023-03-21 at 2 28 58 PM](https://user-images.githubusercontent.com/94288340/226559949-56d7cb4f-542f-46a7-9cb3-2e924f31937e.jpeg)

### ii) Display the video

![WhatsApp Image 2023-03-21 at 2 28 58 PM](https://user-images.githubusercontent.com/94288340/226559949-56d7cb4f-542f-46a7-9cb3-2e924f31937e.jpeg)





### iii) Display the video by resizing the window

![WhatsApp Image 2023-03-21 at 2 28 59 PM](https://user-images.githubusercontent.com/94288340/226627212-50cf5f6b-783f-49fd-b927-151b22b1bb59.jpeg)






### iv) Rotate and display the video

![WhatsApp Image 2023-03-21 at 2 29 00 PM](https://user-images.githubusercontent.com/94288340/226627369-db2f5a77-7c59-4601-a718-e931d7c9393d.jpeg)






## Result:
Thus the image is accessed from webcamera and displayed using openCV.
