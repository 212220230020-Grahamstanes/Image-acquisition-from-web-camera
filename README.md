### EX NO : 02
### DATE  : 08.04.2022
# <p align="center">Image-Acquisition-from-Web-Camera</p>
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
Use VideoCapture(0) to access web camera

### Step 2:
Use imread to read the video or image

### Step 3:
Use imwrite to save the image

### Step 4:
Use imshow to show the video

### Step 5:
End the program and close the output video windows by pressing 'q'.

<br/>
<br/>

## Program:
``` Python
### Developed By: Graham Stanes A
### Register No: 212220230020

## i) Write the frame as JPG file


import cv2
import numpy as np
cap=cv2.VideoCapture(0)
ret,frame=cap.read()
cv2.imwrite("pic_1.jpg",frame)
cap.release()
cv2.destroyAllWindows()


## ii) Display the video


import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('frame',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()


## iii) Display the video by resizing the window


import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2,:width//2]=smaller_frame
    image[height//2: , :width//2]=smaller_frame
    image[:height//2,width//2:]= smaller_frame
    image[height//2:,width//2:]=smaller_frame
    cv2.imshow('frame',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()


## iv) Rotate and display the video

import cv2
import numpy as np
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2,:width//2]=image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    image[height//2: , :width//2]=smaller_frame
    image[:height//2,width//2:]= image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    image[height//2:,width//2:]=smaller_frame
    cv2.imshow('frame',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```
## Output

### i) Write the frame as JPG image

![Screenshot (13)](https://user-images.githubusercontent.com/75235488/161477012-5b919f6e-36da-4927-bbc0-644dc6000388.png)

### ii) Display the video

![Screenshot (14)](https://user-images.githubusercontent.com/75235488/161477037-4d807f9d-c1b0-41f9-bca1-2b38264e4586.png)

### iii) Display the video by resizing the window

![Screenshot (15)](https://user-images.githubusercontent.com/75235488/161477060-b9312bb4-3ce7-4f12-8b4d-fadb1516a2cc.png)

<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>

### iv) Rotate and display the video

![Screenshot (18)](https://user-images.githubusercontent.com/75235488/161477085-d0c6aca2-becf-467b-a367-65e0dfac7a75.png)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
