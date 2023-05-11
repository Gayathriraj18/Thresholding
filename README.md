# Thresholding of Images
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

# Step1:
Improt the packages.

# Step2:
convert to grayscale.

# Step3:
Use global thresholding techniques.

# Step4:
Use adaptive thresholding and otsu's method.

# Step5:
Display the results using loop.
## Program
```python
Developed by: Gayathri A
Reg.no : 212221230028
# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2


# Read the Image and convert to grayscale

image = cv2.imread("spidy.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("spidy.jpg",0)


# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Otsu's method to segment the image 
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

# Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

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


![d9 1](https://github.com/Gayathriraj18/Thresholding/assets/94154854/f5bc6464-01dd-4d62-be77-7f9fb1a1397d)


### Global Thresholding

![d9 2](https://github.com/Gayathriraj18/Thresholding/assets/94154854/0af53f29-2d30-42a1-8211-e33a53855160)

![d9 3](https://github.com/Gayathriraj18/Thresholding/assets/94154854/e72d41ea-cb09-495b-a3cf-a0d5fee86826)


![d9 4](https://github.com/Gayathriraj18/Thresholding/assets/94154854/3f7d1afe-fd26-4022-a47b-1b8a2a447b5f)


![d9 5](https://github.com/Gayathriraj18/Thresholding/assets/94154854/5d40a7a0-3912-473a-98ed-8a5dbfb26a85)




### Adaptive Thresholding

![d9 7](https://github.com/Gayathriraj18/Thresholding/assets/94154854/b33a5393-beaa-4146-abae-8fed12d13414)




### Optimum Global Thesholding using Otsu's Method

![d9 9](https://github.com/Gayathriraj18/Thresholding/assets/94154854/d93f8b3e-cab6-4221-833e-72c7a1c2b9d5)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

