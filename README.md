# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Import required libraries.

### Step2:
Read the image and convert it to grayscale then display it.

### Step3:
Use Global thresholding to segment the image

### Step4:
Use Adaptive thresholding to segment the image

### Step5:
Use Otsu's method to segment the image 

### Step6:
End the program.

## Program

```python

# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image = cv2.imread('image.jpg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Use Global thresholding to segment the image
ret_global, th_global = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Use Adaptive thresholding to segment the image
th_adaptive = cv2.adaptiveThreshold(gray_image, 255, cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY, 11, 2)

# Use Otsu's method to segment the image 
ret_otsu, th_otsu = cv2.threshold(gray_image, 0, 255, cv2.THRESH_BINARY + cv2.THRESH_OTSU)


# Display the results

plt.imshow(th_global, cmap='gray')
plt.title('Global Thresholding (v=127)')
plt.xticks([]), plt.yticks([])
plt.show()

plt.imshow(th_adaptive, cmap='gray')
plt.title('Adaptive Gaussian Thresholding')
plt.xticks([]), plt.yticks([])
plt.show()

plt.imshow(th_otsu, cmap='gray')
plt.title("Otsu's Thresholding")
plt.xticks([]), plt.yticks([])
plt.show()

```
## Output

### Original Image

![image](https://github.com/user-attachments/assets/06917f55-55bc-4566-8c66-9851027b0c58)

### Global Thresholding

![image](https://github.com/user-attachments/assets/b910d85b-5d47-4c7b-9a2f-ea2ab86f5d38)

### Adaptive Thresholding

![image](https://github.com/user-attachments/assets/424ab0e6-09cf-414b-b2f7-bb48c0bdfb04)

### Optimum Global Thesholding using Otsu's Method

![image](https://github.com/user-attachments/assets/b5ba4993-2c2d-479e-a9af-817d94866426)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
