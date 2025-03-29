# IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import necessary libraries such as OpenCV, NumPy, and Matplotlib for image processing and visualization.
<br>

### Step2:
Read the input image using cv2.imread() and store it in a variable for further processing.
<br>

### Step3:
Apply various transformations like translation, scaling, shearing, reflection, rotation, and cropping by defining corresponding functions:

1.Translation moves the image along the x or y-axis.

2.Scaling resizes the image by scaling factors.

3.Shearing distorts the image along one axis.

4.Reflection flips the image horizontally or vertically.

5.Rotation rotates the image by a given angle.
<br>

### Step4:
Display the transformed images using Matplotlib for visualization. Convert the BGR image to RGB format to ensure proper color representation.
<br>

### Step5:
Save or display the final transformed images for analysis and use plt.show() to display them inline in Jupyter or compatible environments.
<br>

## Program:
```python
Developed By: Mohan S
Register Number: 212223240094

```python
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Load the image
image = cv2.imread('Lion.jpg')
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB) 
```
i)Image Translation
```python
rows, cols, _ = image.shape
M_translate = np.float32([[1, 0, 50], [0, 1, 100]])  # Translate by (50, 100) pixels
translated_image = cv2.warpAffine(image_rgb, M_translate, (cols, rows))
plt.imshow(translated_image)
plt.title("Translated Image")
plt.axis('off')
```

ii) Image Scaling
```python
scaled_image = cv2.resize(image_rgb, None, fx=1.5, fy=1.5, interpolation=cv2.INTER_LINEAR) 
plt.imshow(scaled_image)
plt.title("Scaled Image")
plt.axis('off')
```

iii)Image shearing
```python
M_shear = np.float32([[1, 0.5, 0], [0.5, 1, 0]])  
sheared_image = cv2.warpAffine(image_rgb, M_shear, (int(cols * 1.5), int(rows * 1.5)))
plt.imshow(sheared_image)
plt.title("Sheared Image")
plt.axis('off')
```

iv)Image Reflection
```python
reflected_image = cv2.flip(image_rgb, 1)  # Horizontal reflection (flip along y-axis)
plt.imshow(reflected_image)
plt.title("Reflected Image")
plt.axis('off')
```

v)Image Rotation
```python
M_rotate = cv2.getRotationMatrix2D((cols / 2, rows / 2), 45, 1)  
rotated_image = cv2.warpAffine(image_rgb, M_rotate, (cols, rows))
plt.imshow(rotated_image)
plt.title("Rotated Image")
plt.axis('off')
```

vi)Image Cropping
```python
cropped_image = image_rgb[50:300, 100:400]  
plt.figure(figsize=(4, 4))
plt.imshow(cropped_image)
plt.title("Cropped Image")
plt.axis('off')
plt.show()
```

## Output:

### Original Image:
![Screenshot 2025-03-29 143054](https://github.com/user-attachments/assets/189b7fb5-6b9d-4bd2-9a0f-a396fef0c1e0)


### i)Image Translation
![Screenshot 2025-03-29 143125](https://github.com/user-attachments/assets/ae649ccd-7092-415d-8a01-74ef28cd51a1)



### ii) Image Scaling
![Screenshot 2025-03-29 143159](https://github.com/user-attachments/assets/cb7e75bd-67fc-4737-b558-74b1cca1f835)


### iii)Image shearing
![Screenshot 2025-03-29 143232](https://github.com/user-attachments/assets/eba244a7-def6-4685-b450-3fbb0c268e62)



### iv)Image Reflection
![Screenshot 2025-03-29 143256](https://github.com/user-attachments/assets/fd885f5c-46dd-43e8-9222-4544b82d3390)



### v)Image Rotation
![Screenshot 2025-03-29 143319](https://github.com/user-attachments/assets/455e306c-cc36-4903-8e1d-f2bafaa226eb)


### vi)Image Cropping
![Screenshot 2025-03-29 143344](https://github.com/user-attachments/assets/e2916bfd-46bb-45aa-9a9e-f257e31281a0)



## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
