# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1
Import the required libraries.

### Step2
Read the image by using imread().

### Step3
Apply the required filters for the image separately.

### Step4
Plot the original and filtered image by using matplotlib.pyplot.

### Step5
End the program.

## Program:
### Developed By   :pochireddy.p
### Register Number:212223240115
</br>

### 1. Smoothing Filters

i) Using Averaging Filter
```Python


import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("bike.jpg")
img1 = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
kernal = np.ones((11,11),np.float32)/121
img2 = cv2.filter2D(img1,-1,kernal)

plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(img1)
plt.title('original')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(img2)
plt.title('Filtered')
plt.axis('off')




```
### ii) Using Weighted Averaging Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("bike.jpg")
img1 = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
kernal2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16
img2 = cv2.filter2D(img1,-1,kernal2)

plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(img1)
plt.title('original')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(img2)
plt.title('Filtered')
plt.axis('off')


```
### iii) Using Gaussian Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("bike.jpg")
img1 = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
gaussian_blur =  cv2.GaussianBlur(src=img1,ksize=(11,11),sigmaX=0,sigmaY=0)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(img1)
plt.title('original')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(gaussian_blur)
plt.title('Filtered')
plt.axis('off')

```

### iv) Using Median Filter
```Python
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("bike.jpg")
img1 = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
median = cv2.medianBlur(src=img1,ksize=11)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(img1)
plt.title('original')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(median)
plt.title('Filtered')
plt.axis('off')

```

### 2. Sharpening Filters
### i) Using Laplacian Kernal
```Python

import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("bike.jpg")
img1 = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
kernal3 = np.array([[0,1,0],[1,-4,1],[0,1,0]])
img3 = cv2.filter2D(img1,-1,kernal3)

plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(img1)
plt.title('original')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(img3)
plt.title('Filtered')
plt.axis('off')

```
### ii) Using Laplacian Operator
```Python

import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("bike.jpg")
img1 = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
kernal3 = np.array([[0,1,0],[1,-4,1],[0,1,0]])
img3 = cv2.filter2D(img1,-1,kernal3)
new_img = cv2.Laplacian(img1,cv2.CV_64F)

plt.figure(figsize = (9,9))
plt.subplot(1,2,1)
plt.imshow(img1)
plt.title('original')
plt.axis('off')

plt.subplot(1,2,2)
plt.imshow(new_img)
plt.title('Filtered')
plt.axis('off')

```

## OUTPUT:
### 1. Smoothing Filters


i) Using Averaging Filter

![image](https://github.com/pochireddyp/Implementation-of-filter/assets/150232043/d40a8140-2fdc-43e1-8976-659d35f50cb4)


ii) Using Weighted Averaging Filter

![image](https://github.com/pochireddyp/Implementation-of-filter/assets/150232043/f98de5ce-aebf-42aa-b81d-8b0bf407e435)

iii) Using Gaussian Filter


![image](https://github.com/pochireddyp/Implementation-of-filter/assets/150232043/b46e2ad1-2870-48a4-85a1-29b9ab70e26e)

iv) Using Median Filter


![image](https://github.com/pochireddyp/Implementation-of-filter/assets/150232043/8d7368f1-acf5-48c7-9d3d-d532a35fdf14)

### 2. Sharpening Filters


i) Using Laplacian Kernal

![image](https://github.com/pochireddyp/Implementation-of-filter/assets/150232043/851ae6c8-3048-4d0e-8f88-dd3a645a9ac1)


ii) Using Laplacian Operator

![image](https://github.com/pochireddyp/Implementation-of-filter/assets/150232043/4435e305-f5e4-4614-b971-b233a1d724ba)


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
