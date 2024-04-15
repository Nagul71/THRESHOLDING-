## EX-08 THRESHOLDING
### Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.


### Software Required
1. Anaconda - Python 3.7
2. OpenCV
 
### Algorithm
#### Step1:
Load the necessary packages.
#### Step2:
Read the Image and convert to grayscale.
#### Step3:
Use Global thresholding to segment the image.
#### Step4:
Use Adaptive thresholding to segment the image.
#### Step5:
Use Otsu's method to segment the image and display the results.
### Program
```python
DEVELOPED BY: NAGUL K
REGISTER NO: 212222230089
```
#### Load the necessary packages
```python
import numpy as np
import matplotlib.pyplot as plt
import cv2
```
#### Read the Image and convert to grayscale
```python
image = cv2.imread("lion.jpg",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("lion.jpg",0)
```
#### Use Global thresholding to segment the image
```python
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)
```
#### Use Adaptive thresholding to segment the image
```python
thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)
```
#### Use Otsu's method to segment the image 
```python
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```
#### Display the results
```python
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

### Output
#### Original Image
![image](https://github.com/Nagul71/THRESHOLDING-/assets/118661118/30d93d20-2628-44a0-b1b9-671d900b9329)


#### Global Thresholding

![image](https://github.com/Nagul71/THRESHOLDING-/assets/118661118/f5307ca5-7048-4d0c-960f-94a1f8fa4fec)


![image](https://github.com/Nagul71/THRESHOLDING-/assets/118661118/84c92a58-6fef-4937-b5ec-b3463cc4acb2)

![image](https://github.com/Nagul71/THRESHOLDING-/assets/118661118/d8dfbfff-ee55-4272-8a1c-f3563fb1d444)

![image](https://github.com/Nagul71/THRESHOLDING-/assets/118661118/0002a29a-c65f-42f8-9b7a-50483f8323d1)

![image](https://github.com/Nagul71/THRESHOLDING-/assets/118661118/729fa147-eafe-4f4c-a021-e3e89ee8f3b5)











#### Adaptive Thresholding
![image](https://github.com/Nagul71/THRESHOLDING-/assets/118661118/d5ede963-d9cd-4ed4-a45d-6e8dbe47aeee)
![image](https://github.com/Nagul71/THRESHOLDING-/assets/118661118/34dfe6f9-e445-4462-a1b5-1a3b73e6da64)



#### Optimum Global Thesholding using Otsu's Method
![image](https://github.com/Nagul71/THRESHOLDING-/assets/118661118/df1e52d2-0c66-4046-9640-cc3ff969f007)



### Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.


