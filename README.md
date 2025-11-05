# Implementation-of-Erosion-and-Dilation
# Developed By: Daniel C
# Reg no: 212223240023
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Import the necessary packages

### Step2:
Create the Text using cv2.putText

### Step3:
Create the Text using cv2.putText

### Step4:
Create the structuring element

### Step5:
Erode the image

 # step6:
 Dilate the image

## Program:

``` Python
# developed by:Daniel C
# reg no:212223240023

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Create background with Barca-style stripes
image = np.zeros((400, 800, 3), dtype="uint8")

# Create maroon and blue vertical stripes
for i in range(0, 800, 100):
    color = (255, 0, 0) if (i // 100) % 2 == 0 else (0, 0, 139)  # BGR
    image[:, i:i+100] = color

# Add yellow text like Messi's jersey
text = "DANIEL"
text2 = "10"
font = cv2.FONT_HERSHEY_SIMPLEX

cv2.putText(image, text, (220, 150), font, 2.5, (0, 255, 255), 8, cv2.LINE_AA)
cv2.putText(image, text2, (270, 370), font, 5, (0, 255, 255), 12, cv2.LINE_AA)

# Define kernel
kernel = cv2.getStructuringElement(cv2.MORPH_RECT, (5, 5))

# Apply erosion and dilation
eroded_image = cv2.erode(image, kernel, iterations=1)
dilated_image = cv2.dilate(image, kernel, iterations=1)

# Convert to RGB for Matplotlib
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
eroded_image_rgb = cv2.cvtColor(eroded_image, cv2.COLOR_BGR2RGB)
dilated_image_rgb = cv2.cvtColor(dilated_image, cv2.COLOR_BGR2RGB)

# Display results
plt.figure(figsize=(15, 5))

plt.subplot(1, 3, 1)
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis("off")

plt.subplot(1, 3, 2)
plt.imshow(eroded_image_rgb)
plt.title("Eroded Image")
plt.axis("off")

plt.subplot(1, 3, 3)
plt.imshow(dilated_image_rgb)
plt.title("Dilated Image")
plt.axis("off")

plt.tight_layout()
plt.show()

```
## Output:

### Display the input Image
<img width="561" height="327" alt="image" src="https://github.com/user-attachments/assets/d99bf47a-3f0a-4a12-922d-d282f4852fa5" />


### Display the Eroded Image
<img width="562" height="322" alt="image" src="https://github.com/user-attachments/assets/35b2aec9-35fa-4443-8c9c-b6a3954f6919" />


### Display the Dilated Image
<img width="554" height="334" alt="image" src="https://github.com/user-attachments/assets/efc812f9-5b05-4e56-91d2-692a06204258" />


## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
