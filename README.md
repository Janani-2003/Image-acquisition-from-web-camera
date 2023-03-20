# Image-Acquisition-from-Web-Camera
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
``` Python
### Developed By: Janani.R
### Register No:21222120039

## i) Write the frame as JPG file
~~~
import cv2
img = cv2.VideoCapture(0)
while(True):
    imagee,frame = img.read()
    cv2.imshow('myimage',frame)
    if cv2.waitKey(1) == ord('c'):
        break
img.release()
cv2.destroyAllWindows()
~~~

## ii) Display the video
~~~
import cv2
video = cv2.VideoCapture(0)
while (True):
    cap,frame=video.read()
    cv2.imshow('Capturing Video',frame)
    if cv2.waitKey(1) == ord('q'):
        break
video.release()
~~~
## iii) Display the video by resizing the window
~~~
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
~~~
## iv) Rotate and display the video
~~~
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
~~~
## Output

### i) Write the frame as JPG image

![2023-03-20 (1)](https://user-images.githubusercontent.com/94288340/226394322-30c908f7-053e-43e4-ac82-68cfc64deaf0.png)

### ii) Display the video

![2023-03-20 (3)](https://user-images.githubusercontent.com/94288340/226394395-06f28b46-4685-4fb4-ac8f-4970ef6811b8.png)

### iii) Display the video by resizing the window

![out3](https://user-images.githubusercontent.com/94288340/226394463-aadeeb6e-7717-433f-b8cf-731750155b1c.jpg)

### iv) Rotate and display the video

![out4](https://user-images.githubusercontent.com/94288340/226394505-962f0d02-5d81-4956-b1e7-d8367297d8c5.jpg)




## Result:
Thus the image is accessed from webcamera and displayed using openCV.
