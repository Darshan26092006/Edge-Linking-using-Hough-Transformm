# EX-07 EDGE LINKING HOUGH TRANSFORM

## DEVELOPED BY: Darshan V
## REGISTER NUMBER: 212224230050


## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read image and convert it to grayscale image.

### Step2:
Find the edges in the image using canny detector and display.

### Step3:
Detect points that form a line using HoughLinesP.

### Step4:
Draw lines on the image.

### Step5:
Display the result.

## Program:


### Read image and convert it to grayscale image
```PY
import numpy as np
import cv2
import matplotlib.pyplot as plt
img=cv2.imread("VI.jpeg",0)
img_c=cv2.imread("VI.jpeg",1)
img_c=cv2.cvtColor(img_c,cv2.COLOR_BGR2RGB)
gray=cv2.cvtColor(img,cv2.COLOR_GRAY2RGB)
gray = cv2.GaussianBlur(gray,(3,3),0)
plt.figure(figsize=(13,13))
plt.subplot(1,2,1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gray)
plt.title("Gray Image")
plt.axis("off")
plt.show()
```
### Find the edges in the image using canny detector and display
```PY
canny=cv2.Canny(gray,120,150)
plt.imshow(canny)
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()
```
### Detect points that form a line using HoughLinesP
```PY
lines=cv2.HoughLinesP(canny,1,np.pi/180,threshold=80,minLineLength=50,maxLineGap=250)
```
### Draw lines on the image
```PY
for line in lines:
    x1,y1,x2,y2=line[0]
    cv2.line(img_c,(x1,y1),(x2,y2),(255,0,0),3)
```
### Display the result
```PY
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()
```
## Output

### Input image and grayscale image

<img width="266" height="411" alt="download" src="https://github.com/user-attachments/assets/1673dda3-194e-42f1-9239-e3dfaee38265" />
<img width="266" height="411" alt="download" src="https://github.com/user-attachments/assets/44af6d52-e016-4fa1-8c68-10b513c7d348" />


<br>

### Canny Edge detector output
<img width="266" height="411" alt="download" src="https://github.com/user-attachments/assets/3e8b4922-2f74-4acd-bc2e-15b20f0b85c2" />



<br>

### Display the result of Hough transform

<img width="266" height="411" alt="download" src="https://github.com/user-attachments/assets/6d2f98f7-6e84-4150-8d83-f531659fed6a" />


<br>

## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
