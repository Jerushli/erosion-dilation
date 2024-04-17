# Implementation-of-Erosion-and-Dilation
## EX NO: 09
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Import the image

### Step2:
Read the colour image and convert it into grayscale

### Step3:
Perform edge detection using canny

### Step4:
Define the kernel size for erosion and dilation

### Step5:
Display all images

## Program:

### Import the necessary packages
```
import cv2
import numpy as np
from matplotlib import pyplot as plt
```
### Create the Text using cv2.putText
```
input_image_path = 'anbu.jpg'
color_image = cv2.imread(input_image_path)
gray_image=cv2.cvtColor(color_image, cv2.COLOR_BGR2GRAY)
edges = cv2.Canny(gray_image, 100, 200) # you can adjust the thresholds as needed
kernel_size = 5
kernel = np.ones((kernel_size, kernel_size), np. uint8)
erosion = cv2.erode(edges, kernel, iterations=1)
dilation = cv2.dilate(edges, kernel, iterations=1)
```
### Create the structuring element
```
plt.figure(figsize=(15, 10))
plt.subplot(2, 3, 1)
plt.imshow(cv2.cvtColor(color_image, cv2.COLOR_BGR2RGB))
plt.title('Original Color Image')
plt.axis('on')
plt.subplot(2, 3, 2)
plt.imshow(gray_image, cmap="gray")
plt.title('Black and white Image')
plt.axis('on')
plt.subplot(2, 3, 3)
plt.imshow(edges, cmap='gray')
plt.title('Edge Segmentation')
plt.axis('on')
```
### Erode the image
```
plt.subplot(2, 3, 4)
plt.imshow(erosion, cmap = 'gray')
plt.title('Erosion')
plt.axis('on')
```
### Dilate the image
```
plt.subplot(2, 3, 5)
plt.imshow(dilation, cmap='gray')
plt.title('Dilation')
plt.axis('on')
plt.show()

```
## Output:

### Display the input Image
![image](https://github.com/Jerushli/erosion-dilation/assets/120041243/07552a8e-4dc8-45ef-ac27-454c5fb1cab9)

### Display the Eroded Image
![image](https://github.com/Jerushli/erosion-dilation/assets/120041243/7198a8a9-d7ea-452e-bbf9-9e55c33cc15b)


### Display the Dilated Image
![image](https://github.com/Jerushli/erosion-dilation/assets/120041243/8ed3617c-383b-4c3a-91a2-3d34956f90b9)

## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
