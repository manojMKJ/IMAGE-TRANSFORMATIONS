# EX-4 IMAGE-TRANSFORMATIONS


## Aim
To perform image transformation such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping using OpenCV and Python.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
<br>
Import numpy module as np and pandas as pd.

### Step2:
<br>
Assign the values to variables in the program.

### Step3:
<br>
Get the values from the user appropriately.


### Step4:
<br>
Continue the program by implementing the codes of required topics.


### Step5:
<br>
Thus the program is executed in google colab.


## Program:
```python
Developed By: Manoj Kumar G
Register Number: 212222230078
i)Image Translation
import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images in Colab
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

# Load an image from URL or file path
image_url = 'lotus.jpg'  
image = cv2.imread(image_url)

# Define translation matrix
tx = 50  # Translation along x-axis
ty = 30  # Translation along y-axis
translation_matrix = np.float32([[1, 0, tx], [0, 1, ty]])  # Create translation matrix

# Apply translation to the image
translated_image = cv2.warpAffine(image, translation_matrix, (image.shape[1], image.shape[0]))

# Display original and translated images
print("Original Image:")
show_image(image)
print("Translated Image:")
show_image(translated_image)


ii) Image Scaling

import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images in Colab
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

# Load an image from URL or file path
image_url = 'cat.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Define scale factors
scale_x = 1.5  # Scaling factor along x-axis
scale_y = 1.5  # Scaling factor along y-axis

# Apply scaling to the image
scaled_image = cv2.resize(image, None, fx=scale_x, fy=scale_y, interpolation=cv2.INTER_LINEAR)

# Display original and scaled images
print("cat.jpg:")
show_image(image)
print("Scaled Image:")
show_image(scaled_image)

iii)Image shearing
import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images in Colab
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

# Load an image from URL or file path
image_url = 'butterfly.jpg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Define shear parameters
shear_factor_x = 0.5  # Shear factor along x-axis
shear_factor_y = 0.2  # Shear factor along y-axis

# Define shear matrix
shear_matrix = np.float32([[1, shear_factor_x, 0], [shear_factor_y, 1, 0]])

# Apply shear to the image
sheared_image = cv2.warpAffine(image, shear_matrix, (image.shape[1], image.shape[0]))

# Display original and sheared images
print("Original Image:")
show_image(image)
print("Sheared Image:")
show_image(sheared_image)


iv)Image Reflection

import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images in Colab
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

# Load an image from URL or file path
image_url = 'red.jpeg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Reflect the image horizontally
reflected_image_horizontal = cv2.flip(image, 1)

# Reflect the image vertically
reflected_image_vertical = cv2.flip(image, 0)

# Reflect the image both horizontally and vertically
reflected_image_both = cv2.flip(image, -1)

# Display original and reflected images
print("Original Image:")
show_image(image)
print("Reflected Horizontally:")
show_image(reflected_image_horizontal)
print("Reflected Vertically:")
show_image(reflected_image_vertical)
print("Reflected Both:")
show_image(reflected_image_both)


v)Image Rotation

import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images in Colab
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

# Load an image from URL or file path
image_url = 'mixed.jpeg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Define rotation angle in degrees
angle = 45

# Get image height and width
height, width = image.shape[:2]

# Calculate rotation matrix
rotation_matrix = cv2.getRotationMatrix2D((width / 2, height / 2), angle, 1)

# Perform image rotation
rotated_image = cv2.warpAffine(image, rotation_matrix, (width, height))

# Display original and rotated images
print("Original Image:")
show_image(image)
print("Rotated Image:")
show_image(rotated_image)


vi)Image Cropping
import cv2
import numpy as np
from matplotlib import pyplot as plt

# Function to display images in Colab
def show_image(image):
    plt.figure(figsize=(6, 6))
    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis('off')
    plt.show()

# Load an image from URL or file path
image_url = 'green.jpeg'  # Replace with your image URL or file path
image = cv2.imread(image_url)

# Define cropping coordinates (x, y, width, height)
x = 100  # Starting x-coordinate
y = 50   # Starting y-coordinate
width = 200  # Width of the cropped region
height = 150  # Height of the cropped region

# Perform image cropping
cropped_image = image[y:y+height, x:x+width]

# Display original and cropped images
print("Original Image:")
show_image(image)
print("Cropped Image:")
show_image(cropped_image)




```
## Output:
### i)Image Translation
Original image:
![311489746-3169bf4c-fcf3-4cee-ba72-68b6fd9a5774](https://github.com/divakar618/IMAGE-TRANSFORMATIONS/assets/121932143/7ee071b6-de42-45f2-a2b7-7facd28765c7)

Translated image:
![311489746-3169bf4c-fcf3-4cee-ba72-68b6fd9a5774](https://github.com/divakar618/IMAGE-TRANSFORMATIONS/assets/121932143/bbfbb357-5d7d-48fb-acf4-987772ae1ed2)


### ii) Image Scaling
![311489857-cca3b8d5-4356-4215-81a6-825e302a611c](https://github.com/divakar618/IMAGE-TRANSFORMATIONS/assets/121932143/031ba68d-758c-40b0-9772-94facadc5011)



### iii)Image shearing
![311490017-85255e86-2fc9-4658-81f9-d359d35f9bfb](https://github.com/divakar618/IMAGE-TRANSFORMATIONS/assets/121932143/be1a20f3-0a84-4f0a-a60a-311cdf8b4da0)



### iv)Image Reflection
![311490229-d4bde403-6ed2-4503-8e14-28eed3b03c57](https://github.com/divakar618/IMAGE-TRANSFORMATIONS/assets/121932143/c67ee155-fc71-4210-91bd-a19f111b3fc9)



### v)Image Rotation
![311490405-76bb31a0-9772-494e-acf6-e67f95bbda4a](https://github.com/divakar618/IMAGE-TRANSFORMATIONS/assets/121932143/1b1409f5-d61e-4b82-88e5-e740181a39b1)



### vi)Image Cropping

![311490600-90e2e350-d1fc-47b3-a20b-347bb8cf6ce0](https://github.com/divakar618/IMAGE-TRANSFORMATIONS/assets/121932143/7cc5e8ec-cbda-403d-aff1-e9ea3f9321a6)




## Result: 

Thus the different image transformations such as Translation, Scaling, Shearing, Reflection, Rotation and Cropping are done using OpenCV and python programming.
