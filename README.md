## Title: Canny Edge Detection – OpenCV Implementation

### Description:
This project demonstrates the implementation of the Canny Edge Detection algorithm using Python and OpenCV. The Canny technique is widely used to extract edges and boundaries of objects in an image.

### What is Canny Edge Detection?
Canny Edge Detection is a multi-step algorithm that detects sharp intensity changes.
The output is a binary edge map where:
• White pixels = edges
• Black pixels = background

The algorithm includes:

Gaussian smoothing

Gradient calculation

Non-maximum suppression

Double thresholding

Edge tracking by hysteresis

### Project Structure:
Canny-Edge-Detection
• sample.jpg
• canny_edge_detection.ipynb
• README.txt

### How to Run:

Install dependencies
pip install opencv-python matplotlib

Place an image in the project folder and rename it as:
sample.jpg

Open and run the Jupyter notebook:
canny_edge_detection.ipynb

Python Code:
```
import cv2
import matplotlib.pyplot as plt

img = cv2.imread("sample.jpg", 0)

if img is None:
 raise ValueError("Image not found. Check file name.")

edges = cv2.Canny(img, 100, 200)

plt.figure(figsize=(8,4))

plt.subplot(1,2,1)
plt.title("Original Image")
plt.imshow(img, cmap='gray')
plt.axis('off')

plt.subplot(1,2,2)
plt.title("Canny Edges")
plt.imshow(edges, cmap='gray')
plt.axis('off')

plt.show()
```

### Output Explanation:
• Original Image – the grayscale version of your input image
• Canny Output – thin white lines showing object boundaries, with noise removed

Canny detects strong intensity changes and displays only the essential outlines.

How Parameter Settings Affect Results:

The function uses two thresholds:
Canny(image, lower_threshold, upper_threshold)

Lower threshold:
• Lower value → more edges, more noise
• Higher value → fewer edges, cleaner result

Upper threshold:
• Lower value → weak edges included
• Higher value → only strong edges shown, small details lost

A good general setting is 100–200.

### Implementation: 
Python + OpenCV