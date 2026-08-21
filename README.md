# DIPT-EXP-6
# edge-detection-opencv
## Aim
To perform edge detection using Sobel, Roberts, Prewitt, Laplacian, and Canny edge detectors.

## Software Required

Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)
NumPy
Matplotlib

## Algorithm
Step 1:
Import all the necessary modules for the program.

Step 2:
Load an image using cv2.imread().

Step 3:
Convert the image to grayscale.

Step 4:
Apply Sobel operator using OpenCV to detect edges.

Step 5:
Apply Prewitt operator using custom kernels.

Step 6:
Apply Roberts operator using custom kernels.

Step 7:
Apply Laplacian operator using OpenCV.

Step 8:
Apply Canny edge detector using OpenCV.

Step 9:
Display all edge-detected images for comparison.

## Developed By
### Name: VD Natchathira
### Register No: 212224230178

## Output
### Sobel Edge Detector
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("C:/Users/admin/Pictures/Screenshots/Screenshot 2026-08-20 193909.png") 
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original Image')
plt.axis('off')
```
<img width="502" height="400" alt="image" src="https://github.com/user-attachments/assets/ba171cb6-3d96-4b0c-8898-ea9882eb9fa2" />

### Prewitt Edge Detector
```
sobel_x = cv2.Sobel(gray_image, cv2.CV_64F, 1, 0, ksize=5)  
sobel_y = cv2.Sobel(gray_image, cv2.CV_64F, 0, 1, ksize=5)  
sobel_combined = cv2.magnitude(sobel_x, sobel_y)  
plt.imshow(sobel_combined, cmap='gray')
plt.title('Sobel Edge Detection')
plt.axis('off')
```
<img width="506" height="405" alt="image" src="https://github.com/user-attachments/assets/718d8b47-6e14-417a-8d20-a0665feae21d" />

### Roberts Edge Detector
```
laplacian = cv2.Laplacian(gray_image, cv2.CV_64F)

plt.imshow(laplacian, cmap='gray')
plt.title('Laplacian Edge Detection')
plt.axis('off')
plt.show()
```
<img width="315" height="384" alt="image" src="https://github.com/user-attachments/assets/18d91e6f-8c9a-4876-a16b-c1166bf32b6b" />

### Laplacian Edge Detector
```
canny_edges = cv2.Canny(gray_image, 50, 150)

plt.imshow(canny_edges, cmap='gray')
plt.title('Canny Edge Detection')
plt.axis('off')
plt.show()
```
<img width="328" height="384" alt="image" src="https://github.com/user-attachments/assets/a6483424-3b4c-4779-abe8-9791e90ba19c" />

### Canny Edge Detector
```
image = cv2.imread("C:/Users/admin/Pictures/Screenshots/Screenshot 2026-08-20 193909.png")

gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
prewitt_x = np.array([[1, 0, -1],
                      [1, 0, -1],
                      [1, 0, -1]])

prewitt_y = np.array([[1, 1, 1],
                      [0, 0, 0],
                      [-1, -1, -1]])

prewitt_x_edge = cv2.filter2D(gray, -1, prewitt_x)
prewitt_y_edge = cv2.filter2D(gray, -1, prewitt_y)
prewitt = cv2.magnitude(prewitt_x_edge.astype(np.float32),
                        prewitt_y_edge.astype(np.float32))

plt.imshow(canny_edges, cmap='gray')
plt.title('Prewitt Edge Detection')
plt.axis('off')
```
<img width="470" height="427" alt="Screenshot 2026-08-20 202329" src="https://github.com/user-attachments/assets/c3a10f28-2c7a-4f93-88f3-c77e6dbb9ef3" />

## Result

Thus, edges are successfully detected using Sobel, Prewitt, Roberts, Laplacian, and Canny edge detection techniques. Each method highlights edges differently based on gradient and intensity variations, improving feature extraction and analysis.
