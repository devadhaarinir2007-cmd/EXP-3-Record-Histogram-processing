# EXP-3-Histogram-Equalization-Using-OpenCV-Grayscale-Color-Images
## Aim:
To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

1.Read and display a grayscale image
2.Plot histogram of the grayscale image
3.Apply histogram equalization on grayscale image
4.Read and display a color image
5.Plot histogram of B, G, R channels
6.Convert image to HSV color space
7.Apply histogram equalization on the Value (V) channel
8.Convert the enhanced image back to BGR format
9.Display original and enhanced images with histograms

## Software Used:
Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)
NumPy
Matplotlib

## Algorithm:
### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image parrot.jpg in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using cv2.equalizeHist() to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

## Program
Developed By:
Name: DEVADHAARINI.R
Register No :212225040061.
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread('download.jpg', cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
```
```
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```
```
img_eq = cv2.equalizeHist(img)
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
```
```
img = cv2.imread('download.jpg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.imshow(img_eq[:,:,::-1]) 
plt.title('Equalized Image')
plt.show()
```
```
plt.hist(img_eq.ravel(),256,range = [0, 256])
plt.title('Histogram Equalized')
plt.show()
```
```
plt.figure(figsize = (20,10))
plt.subplot(221)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')
plt.subplot(222)
plt.imshow(img_eq[:, :, ::-1])
plt.title('Equalized Image')
plt.subplot(223)
plt.hist(img.ravel(),256,range = [0, 256])
plt.title('Original Image')
plt.subplot(224)
plt.hist(img_eq.ravel(),256,range = [0, 256])
plt.title('Histogram Equalized');plt.show()
```
```
plt.figure(figsize = [15,4])
plt.subplot(121)
plt.hist(img.ravel(),256,range = [0, 256])
plt.title('Original Image')
plt.subplot(122)
plt.hist(img_eq.ravel(),256,range = [0, 256])
plt.title('Histogram Equalized')
```

## Output:
**Grayscale Histogram Equalization**
- Original grayscale image is displayed
<img width="360" height="450" alt="Screenshot 2026-08-07 082238" src="https://github.com/user-attachments/assets/7ba05303-f6a1-480a-90c3-9710971fe19d" />


- Histogram of original grayscale image is plotted
<img width="580" height="449" alt="Screenshot 2026-08-07 082327" src="https://github.com/user-attachments/assets/9f1b2827-23a5-479e-9f9b-9074b58aae81" />


- Enhanced image after histogram equalization is displayed
<img width="589" height="449" alt="Screenshot 2026-08-07 082411" src="https://github.com/user-attachments/assets/d2b576e4-30b0-494a-bb97-cfa550fdee6c" />

- Histogram of enhanced grayscale image shows improved contrast
<img width="360" height="450" alt="Screenshot 2026-08-07 082238" src="https://github.com/user-attachments/assets/1b20984b-610a-4e1b-9bbc-a5ead49ccabe" />

**Color Image Histogram Equalization**
- Original color image is displayed
<img width="365" height="460" alt="Screenshot 2026-08-07 082500" src="https://github.com/user-attachments/assets/d05f53eb-fafd-413c-ad8a-928696e44ae6" />

- Histogram of B, G, R channels is plotted
<img width="600" height="447" alt="Screenshot 2026-08-07 082534" src="https://github.com/user-attachments/assets/3e7dc9c2-d4d8-4698-bef7-bf61ef3650ed" />

- Enhanced image after HSV-based equalization is displayed
<img width="1104" height="585" alt="Screenshot 2026-08-07 082621" src="https://github.com/user-attachments/assets/92a22437-938c-4ba7-80ca-cd73a0e2f3fb" />

- Histogram of enhanced image shows better intensity distribution
<img width="1083" height="345" alt="Screenshot 2026-08-07 082659" src="https://github.com/user-attachments/assets/f01855db-e5f6-4edf-9624-a1fed3ce38f0" />

## Result:
Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
