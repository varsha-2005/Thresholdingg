
# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages

### Step2:
Read the Image and convert to grayscale.

### Step3:
Use Global thresholding to segment the image.

### Step4:

Use Adaptive thresholding to segment the image.

### Step5:
Use Otsu's method to segment the image and display the results.

## Program

#### DEVELOPED BY :Varsha G
#### Register number: 212222230166
```python
# Load the necessary packages
# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2
# Read the Image and convert to grayscale

image = cv2.imread('peacock.jpg',1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread('peacock.jpg',0)


# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 

ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Display the results

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
```
## Output

### Original Image

![101](https://github.com/JananiSoundararajan/Thresholding/assets/119477549/3afe1863-a343-47de-b481-eec303d976a4)


### Global Thresholding

![102](https://github.com/JananiSoundararajan/Thresholding/assets/119477549/3567dfbf-77f2-4d71-a537-3461455a8d9a)

![103](https://github.com/JananiSoundararajan/Thresholding/assets/119477549/1ede4a10-57c2-4b72-a3fb-1e5ddd9e5c30)

![104](https://github.com/JananiSoundararajan/Thresholding/assets/119477549/6e27ac15-e30f-408b-b5b9-20b48bc265c9)

![105](https://github.com/JananiSoundararajan/Thresholding/assets/119477549/3862e803-b6e3-40fc-a8a1-e8b564595e54)

![106](https://github.com/JananiSoundararajan/Thresholding/assets/119477549/2826d730-bfc0-4648-84ae-ea7b2be9fe17)

### Adaptive Thresholding

![107](https://github.com/JananiSoundararajan/Thresholding/assets/119477549/874a0832-3c8c-48e3-b965-c95ba289496b)

![108](https://github.com/JananiSoundararajan/Thresholding/assets/119477549/96b81bb5-e8d7-41b9-b241-d63d4090b659)


### Optimum Global Thesholding using Otsu's Method

![109](https://github.com/JananiSoundararajan/Thresholding/assets/119477549/f1741408-0329-4a5a-979c-8e9a93c0af48)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
