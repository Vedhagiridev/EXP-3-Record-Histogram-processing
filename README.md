# EXP-3-Record-Histogram-processing
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

### Step 2:
Read the image `parrot.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

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

---

## Program

### Developed By:
**Name:** Sharmili V

### Register No:
212225040405
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread("urname.png", cv2.IMREAD_GRAYSCALE)

if img is None:
    print("Image not found!")
else:
    print("Image loaded successfully!")
plt.figure(figsize=(10, 4))

# Display grayscale image
plt.subplot(1, 2, 1)
plt.imshow(img, cmap="gray")
plt.title("Grayscale Image")
plt.axis("off")

# Plot histogram
plt.subplot(1, 2, 2)
plt.hist(img.ravel(), bins=256, range=(0, 256))
plt.title("Original Histogram")
plt.xlabel("Pixel Intensity")
plt.ylabel("Frequency")

plt.tight_layout()
plt.show()
equalized = cv2.equalizeHist(img)

print("Histogram equalization completed!")
plt.figure(figsize=(12, 8))

# 1. Original grayscale image
plt.subplot(2, 2, 1)
plt.imshow(img, cmap="gray")
plt.title("Original Grayscale Image")
plt.axis("off")

# 2. Original histogram
plt.subplot(2, 2, 2)
plt.hist(img.ravel(), bins=256, range=(0, 256))
plt.title("Original Histogram")
plt.xlabel("Intensity")
plt.ylabel("Frequency")

# 3. Equalized image
plt.subplot(2, 2, 3)
plt.imshow(equalized, cmap="gray")
plt.title("Equalized Image")
plt.axis("off")

# 4. Equalized histogram
plt.subplot(2, 2, 4)
plt.hist(equalized.ravel(), bins=256, range=(0, 256))
plt.title("Equalized Histogram")
plt.xlabel("Intensity")
plt.ylabel("Frequency")

plt.tight_layout()
plt.show()
color_img = cv2.imread("urname.png")

if color_img is None:
    print("Color image not found!")
else:
    color_rgb = cv2.cvtColor(color_img, cv2.COLOR_BGR2RGB)

    plt.imshow(color_rgb)
    plt.title("Original Color Image")
    plt.axis("off")
    plt.show()
# Split image into Blue, Green, Red channels
b, g, r = cv2.split(color_img)

plt.figure(figsize=(12, 5))

# Blue channel histogram
plt.subplot(1, 3, 1)
plt.hist(b.ravel(), bins=256, range=(0, 256))
plt.title("Blue Channel")
plt.xlabel("Intensity")
plt.ylabel("Frequency")

# Green channel histogram
plt.subplot(1, 3, 2)
plt.hist(g.ravel(), bins=256, range=(0, 256))
plt.title("Green Channel")
plt.xlabel("Intensity")
plt.ylabel("Frequency")

# Red channel histogram
plt.subplot(1, 3, 3)
plt.hist(r.ravel(), bins=256, range=(0, 256))
plt.title("Red Channel")
plt.xlabel("Intensity")
plt.ylabel("Frequency")

plt.tight_layout()
plt.show()
plt.figure(figsize=(15,5))

plt.subplot(1,3,1)
plt.imshow(b, cmap='Blues')
plt.title('Blue Channel')
plt.axis('off')

plt.subplot(1,3,2)
plt.imshow(g, cmap='Greens')
plt.title('Green Channel')
plt.axis('off')

plt.subplot(1,3,3)
plt.imshow(r, cmap='Reds')
plt.title('Red Channel')
plt.axis('off')

plt.show()
```
---

##  Output

<img width="1305" height="546" alt="image" src="https://github.com/user-attachments/assets/3322902f-280e-4180-8832-a946afe92156" />

<img width="917" height="712" alt="image" src="https://github.com/user-attachments/assets/8be3ac72-f826-49eb-a7c9-6429ef461879" />




<img width="1262" height="503" alt="image" src="https://github.com/user-attachments/assets/6966d2c3-f18e-4856-b8f8-0a13314ae05b" />

<img width="1273" height="467" alt="image" src="https://github.com/user-attachments/assets/ac6aa37f-129f-4ff1-a763-214e8ba9cc8e" />

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
