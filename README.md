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
### Step 1:

Use VideoCapture(0) to access web camera

### Step 2:

Use imread to read the video or image

### Step 3:

Use imwrite to save the image

### Step 4:

Use imshow to show the image

### Step 5:

End the program and close the output video windows by pressing 'q'

## Program:
``` Python
### Developed By: Aditya JV
### Register No: 212220230002

## i) Write the frame as JPG file

import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow("Master.jpg",frame)
    result = False
    if cv2.waitKey(1) == ord('q'): 
        break
videoCaptureObject.release()
cv2.destroyAllWindows()



## ii) Display the video

import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret,frame = cap.read()
    cv2.imshow('frame', frame)
    if cv2.waitKey(1) == ord('q'): 
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
    
    image=np.zeros(frame.shape, np.uint8)
    smaller_frame=cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    
    cv2.imshow('frame', image)
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
    
    image=np.zeros(frame.shape, np.uint8)
    smaller_frame=cv2.resize(frame, (0,0), fx=0.5, fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=image[height//2:, width//2:] = cv2.rotate(smaller_frame,cv2.cv2.ROTATE_180)
    
    cv2.imshow('frame', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()






```
## Output

### i) Write the frame as JPG image


![Master jpg 09-04-2022 13_20_53](https://user-images.githubusercontent.com/75235386/162562798-e19892eb-7456-422a-8a91-1b0fe64127ee.png)



### ii) Display the video


![frame 09-04-2022 13_16_31](https://user-images.githubusercontent.com/75235386/162562857-873c9b53-4ffb-44f3-b743-b43a2e37dc6c.png)



### iii) Display the video by resizing the window


![frame 09-04-2022 13_17_02](https://user-images.githubusercontent.com/75235386/162562863-a77c1cd0-4b2c-471b-8086-1b01fc2ad8c6.png)



### iv) Rotate and display the video


![frame 09-04-2022 13_17_55](https://user-images.githubusercontent.com/75235386/162562870-d8fb0218-2c21-4ce7-9c73-d1711dceb000.png)



## Result:
Thus the image is accessed from webcamera and displayed using openCV.
