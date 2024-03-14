# Image_Acqusition-_using_Web_Camera
## Aim
  
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import cv2 and capture the viedo using cv2.ViedoCapture(0).

### Step 2:
Write the capture image using cv2.imwrite("NewPicture.jpg",frame).

### Step 3:
Resize the image using cv2.resize(frame,(0,0),fx=0.5,fy=0.5).

### Step 4:
Display the image until the loop gets over.

### Step 5:
Rotate the image using cv2.rotate(smaller_frame,cv2.ROTATE_180)
## Program:
``` Python
### Developed By:Vignesh Kumaran N S 
### Register No:212222230171
```
## i) Write the frame as JPG file
```
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while (True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("img.jpeg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()
```

         OR
```
import cv2

videoCaptureObject = cv2.VideoCapture(0)
max_frames = 4  # Maximum number of frames to capture
frame_count = 0

while frame_count < max_frames:
    ret, frame = videoCaptureObject.read()
    cv2.imwrite(f"img_{frame_count}.jpeg", frame)
    frame_count += 1

videoCaptureObject.release()
cv2.destroyAllWindows()
```



## ii) Display the video
```
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow('myimage',frame)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()
```



## iii) Display the video by resizing the window
```
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
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```



## iv) Rotate and display the video
```
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
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image
![image](https://github.com/22009011/Image_Acqusition-_using_Web_Camera/assets/118343461/e2869e8c-b591-4f9d-8a59-732c481619d5)




### ii) Display the video
![image](https://github.com/22009011/Image_Acqusition-_using_Web_Camera/assets/118343461/862e9153-24b5-4653-b93f-aba0f8a6a328)



### iii) Display the video by resizing the window
![dipt3](https://github.com/22009011/Image_Acqusition-_using_Web_Camera/assets/118343461/1a238db8-c1e4-489e-b859-3f7ffac595fc)





### iv) Rotate and display the video
![image](https://github.com/22009011/Image_Acqusition-_using_Web_Camera/assets/118343461/bf8f7221-12a4-4195-b28b-fcb2a22f31e8)






## Result:
Thus the image is accessed from webcamera and displayed using openCV.
