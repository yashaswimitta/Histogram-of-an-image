# Histogram and Histogram Equalization of an image
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
Step1:
Import the necessary libraries and read two images, Color image and Gray Scale image.

Step2:
Calculate the Histogram of Gray scale image and each channel of the color image.

Step3:
Display the histograms with their respective images.

Step4:
Equalize the grayscale image.

Step5:
Display the grayscale image.

## Program:
```python
# Developed By:YASHASWI MITTA
# Register Number:212221230062
import cv2
import matplotlib.pyplot as plt

# Write your code to find the histogram of gray scale image and color image channels.

Gray_image = cv2.imread('grey.jpg')
color_image = cv2.imread('blue.jpg')
plt.imshow(Gray_image)
plt.show()
plt.imshow(color_image)
plt.show()


# Display the histogram of gray scale image and any one channel histogram from color image

gray_image = cv2.imread("grey.jpg")
color_image = cv2.imread("blue.jpg")
gray_hist = cv2.calcHist([gray_image],[0],None,[256],[0,256])
color_hist = cv2.calcHist([color_image],[0],None,[256],[0,256])
plt.figure()
plt.imshow(gray_image)
plt.show()
plt.title("Histogram")
plt.xlabel("Grayscale Value")
plt.ylabel("Pixel Count")
plt.stem(gray_hist)
plt.show()
plt.imshow(color_image)
plt.show()
plt.title("Histogram of Color Image - Green Channel")
plt.xlabel("Intensity Value")
plt.ylabel("Pixel Count")
plt.stem(color_hist)
plt.show()

# Write the code to perform histogram equalization of the image. 

gray_image = cv2.imread('grey.jpg',0)
equ=cv2.equalizeHist(gray_image)
cv2.imshow('Gray image',gray_image)
cv2.imshow('Equalized Image',equ)
cv2.waitKey(0)
cv2.destroyAllWindows()





```
## Output:
### Input Grayscale Image and Color Image
![output](https://github.com/yashaswimitta/Histogram-of-an-image/blob/main/dip%204%201.jpg)

### Histogram of Grayscale Image and any channel of Color Image
![output](https://github.com/yashaswimitta/Histogram-of-an-image/blob/main/dip%204%202.jpg)

### Histogram Equalization of Grayscale Image
![output](https://github.com/yashaswimitta/Histogram-of-an-image/blob/main/dip%204%203.jpg)

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
