# Histogram Equalization Using OpenCV (Grayscale & Color Images)

---

## Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.
```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('rose.jpg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Rose Image')
plt.axis('off')
plt.show()
```
### Step 2:
Read the image `parrot.jpg` in grayscale format.
```python
plt.hist(img.ravel(), 256, range=[0,256])
plt.title('Original Image Histogram')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')
plt.show()

```

### Step 3:
Display the grayscale image and plot its histogram.
```python
img_eq = cv2.equalizeHist(img)
```
### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.
```python
plt.hist(img_eq.ravel(), 256, range=[0,256])
plt.title('Equalized Histogram')
plt.xlabel('Pixel Intensity')
plt.ylabel('Frequency')
plt.show()
```

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.
```python
plt.imshow(img_eq, cmap='gray')
plt.title('Equalized Rose Image')
plt.axis('off')
plt.show()

```
### Step 6:
Read the same image in color format.
```python
img = cv2.imread('rose.jpg', cv2.IMREAD_COLOR)

plt.imshow(cv2.cvtColor(img, cv2.COLOR_BGR2RGB))
plt.title('Original Rose Image')
plt.axis('off')
plt.show()

img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

```
### Step 7:
Split the image into B, G, R channels and plot their histograms.
```python
img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])
```
### Step 8:
Convert the image from BGR to HSV color space.
```python
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
```
### Step 9:
Apply histogram equalization on the V (Value) channel.
```python
plt.figure(figsize=(10,5))

plt.subplot(121)
plt.imshow(cv2.cvtColor(img, cv2.COLOR_BGR2RGB))
plt.title('Original Rose Image')
plt.axis('off')

plt.subplot(122)
plt.imshow(cv2.cvtColor(img_eq, cv2.COLOR_BGR2RGB))
plt.title('Equalized Rose Image')
plt.axis('off')

plt.show()
```

### Step 10:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.
```python
plt.figure(figsize=(12,10))

plt.subplot(221)
plt.imshow(cv2.cvtColor(img, cv2.COLOR_BGR2RGB))
plt.title('Original Rose Image')
plt.axis('off')

plt.subplot(222)
plt.imshow(cv2.cvtColor(img_eq, cv2.COLOR_BGR2RGB))
plt.title('Equalized Rose Image')
plt.axis('off')

plt.subplot(223)
plt.hist(img.ravel(), 256, range=[0,256])
plt.title('Original Histogram')

plt.subplot(224)
plt.hist(img_eq.ravel(), 256, range=[0,256])
plt.title('Equalized Histogram')

plt.show()
```
---

## Program

### Developed By:
**Name:** Rishab P Doshi 

### Register No:
212224240134  

---

##  Output

<img width="708" height="475" alt="image" src="https://github.com/user-attachments/assets/7a871f4e-69e0-45d7-9a35-76d836423893" />
<img width="777" height="558" alt="image" src="https://github.com/user-attachments/assets/9290d90f-5d42-44e3-9661-9c2a8d9a04b4" />
<img width="778" height="552" alt="image" src="https://github.com/user-attachments/assets/3bac97ba-7e7b-4b89-acc1-2973e25bc687" />
<img width="657" height="468" alt="image" src="https://github.com/user-attachments/assets/bc8cedb1-6953-4215-8d2f-36a51a6fa2b2" />
<img width="660" height="465" alt="image" src="https://github.com/user-attachments/assets/977497e9-65b7-4c69-9cc4-095243342df0" />
<img width="1005" height="347" alt="image" src="https://github.com/user-attachments/assets/f4153256-5b35-411f-8b70-044cde575f78" />
<img width="1088" height="805" alt="image" src="https://github.com/user-attachments/assets/8c9f8f44-30bd-4ff5-8bf6-fb8d01baae5c" />



### Grayscale Histogram Equalization

- Original grayscale image is displayed  
- Histogram of original grayscale image is plotted  
- Enhanced image after histogram equalization is displayed  
- Histogram of enhanced grayscale image shows improved contrast  

### Color Image Histogram Equalization

- Original color image is displayed  
- Histogram of B, G, R channels is plotted  
- Enhanced image after HSV-based equalization is displayed  
- Histogram of enhanced image shows better intensity distribution  

---

## Result

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
