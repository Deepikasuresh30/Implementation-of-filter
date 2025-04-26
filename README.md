# Implementation-of-filter
# Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

# Software Required:
Anaconda - Python 3.7

# Algorithm:
### Step1
Import the required libraries.

### Step2
Convert the image from BGR to RGB.

### Step3
Apply the required filters for the image separately.

### Step4
Plot the original and filtered image by using matplotlib.pyplot.

### Step5
End the program.

# Program:
## Developed By   : Deepika S
## Register Number: 212223230039
```
import cv2
import matplotlib.pyplot as plt
import numpy as np
image1=cv2.imread("C:/Users/admin/Downloads/moon.webp")
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

kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()

gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()

median=cv2.medianBlur(image2,13)
plt.imshow(median)
plt.title("Median Blur")
plt.axis("off")
plt.show()

kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()

laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()
```
# OUTPUT:

![image](https://github.com/user-attachments/assets/b42c53e6-fc76-41a1-9951-a703d64695bf)

![image](https://github.com/user-attachments/assets/55ebfba8-0a3b-4061-b636-eea1bc205739)

![image](https://github.com/user-attachments/assets/dfaf04cd-843b-42f7-b921-7c4fab082ce0)

![image](https://github.com/user-attachments/assets/f0b5602f-2646-4cd7-a2c5-889262a2d388)

![image](https://github.com/user-attachments/assets/2773d17d-9c13-4e09-822a-ab790ffa7ef0)

![image](https://github.com/user-attachments/assets/e70bf368-416e-4a44-aaf3-42e55390460d)

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
