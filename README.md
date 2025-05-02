# Implementation-of-filter
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:

1.Import the required libraries.

2.Convert the image from BGR to RGB.

3.Apply the required filters for the image separately.

4.Plot the original and filtered image by using matplotlib.pyplot.

5.End of Program

## Program:
### Developed By   : HARESH R
### Register Number: 212224040097
</br>

### 1. Smoothing Filters

i) Using Averaging Filter
```Python
# Developed By: HARESH R
# Register Number: 212224040097
import cv2
import matplotlib.pyplot as plt
import numpy as np
import os

img_path = r"C:\Users\admin\Downloads\eif.jpeg"  # Change this to your correct path

if not os.path.exists(img_path):
    print(" Image not found. Check the file path.")
else:
    image1 = cv2.imread(img_path)
    if image1 is None:
        print(" Image could not be loaded (possibly corrupted or unsupported format).")
    else:
        image2 = cv2.cvtColor(image1, cv2.COLOR_BGR2RGB)
        kernel = np.ones((11, 11), np.float32) / 169
        image3 = cv2.filter2D(image2, -1, kernel)

        plt.figure(figsize=(9, 9))
        plt.subplot(1, 2, 1)
        plt.imshow(image2)
        plt.title("Original Image")
        plt.axis("off")

        plt.subplot(1, 2, 2)
        plt.imshow(image3)
        plt.title("Average Filter Image")
        plt.axis("off")
        plt.show()




```
<h2>OUTPUT</h2>

![Screenshot 2025-05-02 233451](https://github.com/user-attachments/assets/7efa0c2b-3d98-494b-a307-65a8b4209a75)



ii) Using Weighted Averaging Filter
```Python
# Developed By: HARESH R
# Register Number: 212224040097

kernel1=np.array([[1,2,1],[2,4,2],[1,2,1]])/16
image3=cv2.filter2D(image2,-1,kernel1)
plt.imshow(image3)
plt.title("Weighted Average Filter Image")
plt.axis("off")
plt.show()





```
<h2>OUTPUT</h2>

![Screenshot 2025-05-02 233511](https://github.com/user-attachments/assets/0403195e-9b00-447c-90be-a3db6a2dc13d)



iii) Using Gaussian Filter
```Python
# Developed By: HARESH R
# Register Number: 212224040097

gaussian_blur=cv2.GaussianBlur(image2,(33,33),0,0)
plt.imshow(gaussian_blur)
plt.title("Gaussian Blur")
plt.axis("off")
plt.show()







```
<h2>OUTPUT</h2>

![Screenshot 2025-05-02 233559](https://github.com/user-attachments/assets/027c8601-71b2-4176-9a88-c1999db89839)



iv)Using Median Filter
```Python

# Developed By: HARESH R
# Register Number: 212224040097

median = cv2.medianBlur(image2, 13)
plt.imshow(cv2.cvtColor(median, cv2.COLOR_BGR2RGB))  # Convert BGR to RGB for correct color display
plt.title("Median Blur")
plt.axis("off")
plt.show()



```
<h2>OUTPUT</h2>

![Screenshot 2025-05-02 233615](https://github.com/user-attachments/assets/a68a770c-8011-4024-99ee-7939b24cf2c0)



### 2. Sharpening Filters
i) Using Laplacian Linear Kernal
```Python
# Developed By: HARESH R
# Register Number: 212224040097

kernel2=np.array([[-1,-1,-1],[2,-2,1],[2,1,-1]])
image3=cv2.filter2D(image2,-1,kernel2)
plt.imshow(image3)
plt.title("Laplacian Kernel")
plt.axis("off")
plt.show()

```
<h2>OUTPUT</h2>

![Screenshot 2025-05-02 233630](https://github.com/user-attachments/assets/6f63dd93-cd56-4530-b113-55730a8ff1c2)



ii) Using Laplacian Operator
```Python


# Developed By: HARESH R
# Register Number: 212224040097

laplacian=cv2.Laplacian(image2,cv2.CV_64F)
plt.imshow(laplacian)
plt.title("Laplacian Operator")
plt.axis("off")
plt.show()


```
<h2>OUTPUT</h2>


![Screenshot 2025-05-02 233650](https://github.com/user-attachments/assets/134821bc-68f3-4ff6-b9ef-03b753403799)


</br>

## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
