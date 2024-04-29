# EX.NO:08 THRESHOLDING
# DATE:
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.
### Step2:
Read the Image and convert to grayscale.
### Step3:
Use Global thresholding to segment the image.
### Step4:
Use Adaptive thresholding to segment the image.
### Step5:
 Use Otsu's method to segment the image.
## Program
```
DEVELOPED BY:PAVANA.G
REGISTER NUMBER: 212222230105
```
- Load the necessary packages
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt
```
- Read the Image and convert to grayscale
```python
image=cv2.imread("exp.jpeg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("exp.jpeg",0)
```
- Use Global thresholding to segment the image
```python
ret,thresh_dipt1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_dipt2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_dipt3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_dipt4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_dipt5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
- Use Adaptive thresholding to segment the image
```python
thresh_dipt7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_dipt8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
- Use Otsu's method to segment the image 
```python
ret,thresh_dipt6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
- Display the results
```python
titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
      ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_dipt1,thresh_dipt2,thresh_dipt3,thresh_dipt4,thresh_dipt5,thresh_dipt6,thresh_dipt7,thresh_dipt8]
plt.title("Original Image")
plt.imshow(image)
plt.axis("off")
plt.show()
for i in range(0,9):
  plt.title(titles[i])
  plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
  plt.axis("off")
  plt.show()
```
## Output
## ORIGINAL IMAGE:
![Screenshot 2024-04-09 145127](https://github.com/gpavana/THRESHOLDING-/assets/118787343/a17a51dd-89aa-4e51-9194-ec0a4300e7a9)
## GRAY IMAGE:
![Screenshot 2024-04-09 145133](https://github.com/gpavana/THRESHOLDING-/assets/118787343/7ab38b59-fa9a-485c-a16d-b67983a4cddf)
## GLOBAL THRESHOLDING:
![Screenshot 2024-04-09 145159](https://github.com/gpavana/THRESHOLDING-/assets/118787343/39b15e07-1346-4869-8e56-756d880c4efc)
![Screenshot 2024-04-09 145206](https://github.com/gpavana/THRESHOLDING-/assets/118787343/7286a4d7-b1e0-44de-97cb-74ae0313f624)
![Screenshot 2024-04-09 145213](https://github.com/gpavana/THRESHOLDING-/assets/118787343/d2721127-dbbf-414b-bc25-d636fe9f1305)
![Screenshot 2024-04-09 145218](https://github.com/gpavana/THRESHOLDING-/assets/118787343/d9d95269-285b-4017-8a83-6133b787d09a)
![Screenshot 2024-04-09 145223](https://github.com/gpavana/THRESHOLDING-/assets/118787343/3ceb7f49-93b7-49b2-b586-64339bf06ca8)
## ADAPTIVE THRESHOLDING:
![Screenshot 2024-04-09 145234](https://github.com/gpavana/THRESHOLDING-/assets/118787343/17770a2e-20a3-43f1-b754-32344ab835b4)
![Screenshot 2024-04-09 145240](https://github.com/gpavana/THRESHOLDING-/assets/118787343/4ea01256-a0db-4244-a592-af45c6b45233)
## OTSU THRESHOLDING:
![Screenshot 2024-04-09 145229](https://github.com/gpavana/THRESHOLDING-/assets/118787343/113ca1af-0140-407a-9af3-6b4cb1c845b9)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
