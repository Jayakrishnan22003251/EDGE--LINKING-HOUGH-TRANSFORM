# EDGE--LINKING-HOUGH-TRANSFORM
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
```
NAME : JAYAKRISHNAN L B L
REGISTER NUMBER : 212222230052
```


### Read image and convert it to grayscale image
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the image in grayscale and color
img = cv2.imread("flower.jpg", 0)
img_c = cv2.imread("flower.jpg", 1)
img_c = cv2.cvtColor(img_c, cv2.COLOR_BGR2RGB)

# Apply Gaussian blur to the grayscale image
gray = cv2.GaussianBlur(img, (3, 3), 0)
plt.figure(figsize=(13, 13))
plt.subplot(1, 2, 1)
plt.imshow(img_c)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1, 2, 2)
plt.imshow(gray, cmap='gray')
plt.title("Gray Image")
plt.axis("off")
plt.show()
```


### Find the edges in the image using canny detector and display
```
canny = cv2.Canny(gray, 120, 150)
plt.imshow(canny, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis("off")
plt.show()

```


### Detect points that form a line using HoughLinesP
```
lines = cv2.HoughLinesP(canny, 1, np.pi / 180, threshold=80, minLineLength=50, maxLineGap=250)
```



### Draw lines on the image

```
for line in lines:
    x1, y1, x2, y2 = line[0]
    cv2.line(img_c, (x1, y1), (x2, y2), (255, 0, 0), 3)
```

### Display the result

```
plt.imshow(img_c)
plt.title("Result Image")
plt.axis("off")
plt.show()

```
## Output

### Input image and grayscale image
![image](https://github.com/Jayakrishnan22003251/EDGE--LINKING-HOUGH-TRANSFORM/assets/120232371/2e0c5d7d-9a1b-42ed-98d8-abb85cce9694)


### Canny Edge detector output

![image](https://github.com/Jayakrishnan22003251/EDGE--LINKING-HOUGH-TRANSFORM/assets/120232371/0998aecc-b39f-4948-8db6-1d426d9eb73b)


### Display the result of Hough transform
![image](https://github.com/Jayakrishnan22003251/EDGE--LINKING-HOUGH-TRANSFORM/assets/120232371/cfd015fc-f814-40b2-b32b-6d2dafe88cdf)




## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
