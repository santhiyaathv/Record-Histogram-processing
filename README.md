# Record-Histogram-processing
## EXP. NO: 03
# Histogram-of-an-images
## NAME : SANTHIYA B
## REG NO: 212224230247

## Aim

To obtain a histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255. Also, write a Python program using OpenCV to perform histogram equalization.

## Software Required

- Anaconda - Python 3.7
- OpenCV
- NumPy
- Matplotlib

## Algorithm

### Step 1
Read the grayscale and color images using the `cv2.imread()` function.

### Step 2
Display the grayscale and color images using the `imshow()` function.

### Step 3
Use the `cv2.calcHist()` function to calculate the frequency of pixel intensities in the grayscale image.

### Step 4
Use the `cv2.calcHist()` function to calculate the histograms of the Blue, Green, and Red channels of the color image.

### Step 5
Plot and display the histograms of the grayscale image and color image.

## Program

```python
```python
# Experiment 3: Histogram Processing

# Step 1: Import required libraries
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 2: Read the grayscale image
img = cv2.imread('pic.jpg', cv2.IMREAD_GRAYSCALE)

# Check whether the image is loaded
if img is None:
    print("Error: Image not found. Check the file name and path.")
else:
    # Step 3: Display the original grayscale image
    plt.figure(figsize=(6, 4))
    plt.imshow(img, cmap='gray')
    plt.title('Original Grayscale Image')
    plt.axis('off')
    plt.show()

    # Step 4: Display the original histogram
    plt.figure(figsize=(6, 4))
    plt.hist(img.ravel(), 256, range=[0, 256])
    plt.title('Original Image Histogram')
    plt.xlabel('Pixel Intensity')
    plt.ylabel('Frequency')
    plt.show()

    # Step 5: Perform histogram equalization
    img_eq = cv2.equalizeHist(img)

    # Step 6: Display the equalized histogram
    plt.figure(figsize=(6, 4))
    plt.hist(img_eq.ravel(), 256, range=[0, 256])
    plt.title('Equalized Histogram')
    plt.xlabel('Pixel Intensity')
    plt.ylabel('Frequency')
    plt.show()

    # Step 7: Display the equalized grayscale image
    plt.figure(figsize=(6, 4))
    plt.imshow(img_eq, cmap='gray')
    plt.title('Histogram Equalized Grayscale Image')
    plt.axis('off')
    plt.show()


# Step 8: Read the color image
img_color = cv2.imread('pic.jpg', cv2.IMREAD_COLOR)

if img_color is None:
    print("Error: Color image not found.")
else:
    # Step 9: Convert the color image from BGR to HSV
    img_hsv = cv2.cvtColor(img_color, cv2.COLOR_BGR2HSV)

    # Step 10: Apply histogram equalization to the brightness channel
    img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])

    # Step 11: Convert HSV back to BGR
    img_eq_color = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

    # Step 12: Display the equalized color image
    plt.figure(figsize=(6, 4))
    plt.imshow(cv2.cvtColor(img_eq_color, cv2.COLOR_BGR2RGB))
    plt.title('Histogram Equalized Color Image')
    plt.axis('off')
    plt.show()

    # Step 13: Display the original and equalized color images
    plt.figure(figsize=(12, 5))

    plt.subplot(1, 2, 1)
    plt.imshow(cv2.cvtColor(img_color, cv2.COLOR_BGR2RGB))
    plt.title('Original Color Image')
    plt.axis('off')

    plt.subplot(1, 2, 2)
    plt.imshow(cv2.cvtColor(img_eq_color, cv2.COLOR_BGR2RGB))
    plt.title('Equalized Color Image')
    plt.axis('off')

    plt.tight_layout()
    plt.show()

    # Step 14: Display the original and equalized histograms
    plt.figure(figsize=(12, 4))

    plt.subplot(1, 2, 1)
    plt.hist(img_color.ravel(), 256, range=[0, 256])
    plt.title('Original Color Image Histogram')
    plt.xlabel('Pixel Intensity')
    plt.ylabel('Frequency')

    plt.subplot(1, 2, 2)
    plt.hist(img_eq_color.ravel(), 256, range=[0, 256])
    plt.title('Equalized Color Image Histogram')
    plt.xlabel('Pixel Intensity')
    plt.ylabel('Frequency')

    plt.tight_layout()
    plt.show()
```




## Output

### Input Grayscale Image
<img width="520" height="552" alt="image" src="https://github.com/user-attachments/assets/464da926-22c5-4fac-8a58-8406c2f6ccb0" />



### Input Grayscale Image Range
<img width="752" height="692" alt="image" src="https://github.com/user-attachments/assets/89a04202-cbcf-40e3-b237-810990b81aa9" />



### Input Grayscale Image Equalized Histogram
<img width="748" height="548" alt="image" src="https://github.com/user-attachments/assets/720f25c0-dde9-41dd-802e-c7221e995d5d" />




### Histogram of Grayscale Image and Color Image Channels
### Original Image
<img width="450" height="536" alt="image" src="https://github.com/user-attachments/assets/c9707afd-cec9-45f1-b344-4932e5366472" />



### Equalized Image
<img width="492" height="540" alt="image" src="https://github.com/user-attachments/assets/cf338f8d-f4e3-476a-82ce-88c521c58b14" />



### Equalized Histogram
<img width="733" height="547" alt="image" src="https://github.com/user-attachments/assets/71b2d416-d8de-4df8-812e-c76171cd17fd" />



### Final Output of Original Image and Equalized 
<img width="1397" height="492" alt="image" src="https://github.com/user-attachments/assets/c14cbbb2-4ead-4df0-bdd3-de249b8d4232" />


### Final Output of Original Image and its Histogram Equalized
<img width="1352" height="412" alt="image" src="https://github.com/user-attachments/assets/b26911cc-6881-4f55-a027-cc749ebdec07" />


 
## Result

Thus, the histogram showing the frequency of pixel intensities ranging from 0 to 255 was obtained for the grayscale image and the color image using OpenCV.
