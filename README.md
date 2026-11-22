# Exp-8-Record-THRESHOLDING-
Image Segmentation Using Thresholding Techniques in OpenCV

Aim

To segment an image using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques using Python and OpenCV.

The program performs the following operations:

Global Thresholding
Adaptive Thresholding
Otsu's Thresholding

Software Used

Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)
NumPy
Matplotlib

Algorithm

Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

Step 2:
Load the input image using OpenCV.

Step 3:
Convert the input image into grayscale format.

Step 4: Global Thresholding
Select a fixed threshold value.
Apply thresholding to separate foreground and background pixels.
Display the thresholded image.
Step 5: Adaptive Thresholding
Compute threshold values for small regions of the image.
Apply Adaptive Mean Thresholding.
Apply Adaptive Gaussian Thresholding.
Display the segmented images.
Step 6: Otsu's Thresholding
Automatically determine the optimal threshold value.
Apply Otsu's thresholding technique.
Display the segmented image.
Step 7:
Compare the results obtained from Global, Adaptive, and Otsu's thresholding methods.

Developed By

Name: MOHANA K.V.S.L

Register No: 212224240093

Program:
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 2: Read the image and convert to grayscale
image = cv2.imread('monaa.jpeg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Original Image
plt.subplot(2, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Original Image")
plt.axis('off')

# Step 3: Global Thresholding
_, global_thresholded = cv2.threshold(gray_image, 127, 255, cv2.THRESH_BINARY)

# Step 4: Adaptive Thresholding
adaptive_thresholded = cv2.adaptiveThreshold(
    gray_image, 255,
    cv2.ADAPTIVE_THRESH_GAUSSIAN_C,
    cv2.THRESH_BINARY, 11, 2
)

# Step 5: Otsu's Method
_, otsu_thresholded = cv2.threshold(
    gray_image, 0, 255,
    cv2.THRESH_BINARY + cv2.THRESH_OTSU
)

# Global Thresholding
plt.subplot(2, 2, 2)
plt.imshow(global_thresholded, cmap='gray')
plt.title("Global Thresholding")
plt.axis('off')

# Adaptive Thresholding
plt.subplot(2, 2, 3)
plt.imshow(adaptive_thresholded, cmap='gray')
plt.title("Adaptive Thresholding")
plt.axis('off')

# Otsu's Method
plt.subplot(2, 2, 4)
plt.imshow(otsu_thresholded, cmap='gray')
plt.title("Otsu's Method")
plt.axis('off')

# Show the plot
plt.tight_layout()
plt.show()
```
Output
Original Grayscale Image

<img width="687" height="920" alt="image" src="https://github.com/user-attachments/assets/54f2768f-f318-4aee-96af-320e05745753" />

Global Thresholding

<img width="775" height="888" alt="image" src="https://github.com/user-attachments/assets/aed784ad-4bb8-4282-b038-8e5db12efbbb" />


Original image is displayed.

Thresholded image is displayed.

A fixed threshold value is used for segmentation.

Pixels are classified as foreground or background.

Adaptive Thresholding

<img width="807" height="881" alt="image" src="https://github.com/user-attachments/assets/392e77c7-6aa6-4f6b-8e54-a96dce28e771" />


Original image is displayed.

Adaptive Mean Thresholded image is displayed.

Adaptive Gaussian Thresholded image is displayed.

Threshold values vary across different regions of the image.
Suitable for images with uneven illumination.

Otsu's Thresholding

<img width="622" height="857" alt="image" src="https://github.com/user-attachments/assets/7317e5ef-b6e1-401a-95bb-71762cd84e9d" />


Original image is displayed.

Otsu segmented image is displayed.

Optimal threshold value is calculated automatically.

Produces improved segmentation for bimodal histograms.

Result

Thus, image segmentation is successfully performed using Global Thresholding, Adaptive Thresholding, and Otsu's Thresholding techniques in OpenCV.
