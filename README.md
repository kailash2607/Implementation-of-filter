# Implementation-of-filter
## Developed By   : KAILASH PRABHU S
## Register Number: 212224240068
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
</br>Import the necessary libraries (cv2, numpy, matplotlib.pyplot) and read the input image using cv2.imread().

</br> 

### Step2
</br>
Define the kernels for the filters, such as an averaging kernel for smoothing (e.g., a 5x5 matrix of ones divided by 25) and a Laplacian kernel for sharpening.

</br> 

### Step3
</br>
Apply the smoothing filters to the original image using functions like cv2.filter2D() for the averaging filter, cv2.GaussianBlur() for Gaussian blur, and cv2.medianBlur() for median blur.

</br> 

### Step4
</br>
Apply the sharpening filter using cv2.filter2D() with the Laplacian kernel, and then add this filtered output to the original image to create the final sharpened image.

</br> 

### Step5
</br>
Display the original, smoothed, and sharpened images side-by-side using matplotlib.pyplot.imshow() and plt.subplot() for comparison.

</br> 

## Program:

</br>

### 1. Smoothing Filters

i) Using Averaging Filter
```Python



import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("k12.jpeg")
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
kernel=np.ones((11,11),np.float32)/169
image3=cv2.filter2D(image2,-1,kernel)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Average Filter Image")
plt.axis("off")
plt.show()






```
ii) Using Weighted Averaging Filter
```Python



kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image2=cv2.cvtColor(image1,cv2.COLOR_BGR2RGB)
image3=cv2.filter2D(image2,-1,kernel1)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()






```
iii) Using Gaussian Filter
```Python





gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()



```
iv)Using Median Filter
```Python



median=cv2.medianBlur(image2,13)
plt.figure(figsize=(9,9))
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()





```

### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```Python



kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()





```
ii) Using Laplacian Operator
```Python




laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.subplot(1,2,1)
plt.imshow(image2)
plt.title("Original Image")
plt.axis("off")
plt.subplot(1,2,2)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()




```

## OUTPUT:
### 1. Smoothing Filters
</br>

i) Using Averaging Filter

<img width="980" height="578" alt="image" src="https://github.com/user-attachments/assets/2d71e1c2-482d-44c2-b5ee-103a7570a1a7" />



ii)Using Weighted Averaging Filter

<img width="701" height="426" alt="image" src="https://github.com/user-attachments/assets/f8cbe330-2503-44bb-bcc2-4a924df7b3cc" />



iii)Using Gaussian Filter

<img width="668" height="430" alt="image" src="https://github.com/user-attachments/assets/23644447-2c98-4e68-9076-8eb1d06cee2c" />


iv) Using Median Filter

<img width="943" height="568" alt="image" src="https://github.com/user-attachments/assets/e1ed19fd-85f3-43d5-81db-fb630bac7636" />



### 2. Sharpening Filters
</br>

i) Using Laplacian Kernal

<img width="666" height="422" alt="image" src="https://github.com/user-attachments/assets/cbe532a5-6877-4ec7-a88a-110e5c8eb8ad" />


ii) Using Laplacian Operator

<img width="690" height="432" alt="image" src="https://github.com/user-attachments/assets/51144b2b-4835-4570-93c5-f9e7446972c9" />



## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
