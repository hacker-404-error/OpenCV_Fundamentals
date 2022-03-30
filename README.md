# What is OpenCV?
- OpenCV is a Python open-source library, which is used for computer vision in Artificial intelligence, Machine Learning, face recognition, etc.
- In OpenCV, the CV is an abbreviation form of a computer vision, which is defined as a field of study that helps computers to understand the content of the digital images such as photographs and videos.

<br>
<div align="center">
    <img src="https://static.javatpoint.com/tutorial/opencv/images/what-is-opencv2.png" alt="Example of openCV">
</div>
<br>

## Installation of the OpenCV
OpenCV is a Python library so it is necessary to install Python in the system and install OpenCV using pip command:

```
pip install opencv-contrib-python --upgrade  
```

We can install it without extra modules by the following command:
```
pip install opencv-python  
```

# Reading Images
OpenCV allows us to perform multiple operations on the image, but to do that it is necessary to read an image file as input, and then we can perform the various operations on it. 

### `imread function`
The imread() function loads image from the specified file and returns it. The syntax is:
```
cv2.imread(filename, flag])  
```

#### `Parameters:`

- `filename`: Name of the file to be loaded

- `flag`: The flag specifies the color type of a loaded image:
  - `IMREAD_COLOR` : If the flag is set to this value, the loaded image will be converted to a 3-channel BGR (Blue Green Red) color image.
  - `IMREAD_GRAYSCALE` : If the flag is set to this value, the loaded image will be converted to a single-channel grayscale image.
  - `IMREAD_LOAD_GDAL` : If the flag is set to this value, you can load the image using the gdal driver.
  - `IMREAD_ANYCOLOR` : If the flag is set to this value, the image is read in any possible color format.
  - `IMREAD_REDUCED_COLOR_2` : If the flag is set to this value, the image is read as three-channel BGR, and the size of the image is reduced to ½, ¼th or ⅛th of the original size of the image with respect to the field used.
  - `IMREAD_REDUCED_GRAYSCALE_2` : If the flag is set to this value, the image is read as a single-channel grayscale image, and the size of the image is reduced to ½, ¼th or ⅛th of the original size of the image with respect to the field used.
  - `IMREAD_UNCHANGED` : If the flag is set to this value, the loaded image is returned as it is.
  
The imread() function returns a matrix, if the image cannot be read because of unsupported file format, missing file, unsupported or invalid format. Currently, the following file formats are supported.
 
- Window bitmaps - *.bmp, *.dib
- JPEG files - *.jpeg, *.jpg, *.jpe
- Portable Network Graphics - *.png
- Portable image format- *.pbm, *.pgm, *.ppm
- TIFF files - *.tiff, *.tif

```
#importing the opencv module  
import cv2  
  
# using imread('path') and 0 denotes read as  grayscale image  
img = cv2.imread(r'C:\Users\DEVANSH SHARMA\cat.jpeg',1)  
  
#This is using for display the image  
cv2.imshow('image',img)  
  
cv2.waitKey(3) # This is necessary to be required so that the image doesn't close immediately.  
#It will run continuously until the key press.  
cv2.destroyAllWindows()  
```

# Save Images
OpenCV imwrite() function is used to save an image to a specified file. The file extension defines the image format. The syntax is the following:
```
cv2.imwrite(filename, img[,params])  
```
#### `Parameters:`
`filename`- Name of the file to be loaded

`image`- Image to be saved.

`params`- The following parameters are currently supported:
  - For JPEG, quality can be from 0 to 100. The default value is 95.
  - For PNG, quality can be the compress level from 0 to 9. The default value is 1.
  - For PPM, PGM, or PBM, it can be a binary format flag 0 or 1. The default value is 1.

```
import cv2  
  
# read image as grey scale  
img = cv2.imread(r'C:\Users\DEVANSH SHARMA\cat.jpeg', 1)  
  
# save image  
status = cv2.imwrite(r'C:\Users\DEVANSH SHARMA\cat.jpeg', 0, img)  
print("Image written to file-system : ", status)  
```


# Playing Video from file
We can play the video from the file. It is similar to capturing from the camera by changing the camera index with the file name. The time must be appropriate for cv2.waitKey() function, if time is high, video will be slow. If time is too less, then the video will be very fast.

```
import numpy as np  
import cv2  
  
cap = cv2.VideoCapture('filename')  
  
while(cap.isOpened()):  
    ret, frame = cap.read()  
#it will open the camera in the grayscale mode  
    gray = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)  
  
    cv2.imshow('frame',gray)  
    if cv2.waitKey(1) & 0xFF == ord('q'):  
        break  
  
cap.release()  
cv2.destroyAllWindows()  
```
# Capture Video from Camera
- OpenCV allows a straightforward interface to capture live stream with the camera (webcam).

- We need to create a VideoCapture object to capture a video. 
- It accepts either the device index or the name of a video file.
- A number which is specifying to the camera is called device index. 
- We can select the camera by passing the O or 1 as an argument. 
- After that we can capture the video frame-by-frame.

```
import cv2  
cap = cv2.VideoCapture(0)  
# Check if camera opened successfully
if (cap.isOpened()== False): 
  print("Error opening video  file")
   
# Read until video is completed
while(cap.isOpened()):
  # Capture frame-by-frame
  ret, frame = cap.read()
  if ret == True:
    # Display the resulting frame
    cv2.imshow('This is my Camera', frame)
    # Press Q on keyboard to  exit
    if cv2.waitKey(1) & 0xFF == ord('q'):
      break
  # Break the loop
  else: 
    break
# When everything done, release 
# the video capture object
cap.release()
# Closes all the frames
cv2.destroyAllWindows() 
```

### Next Topics : 
- [Image Processing in OpenCV]()
- [Video Processing in OpenCV]()
--------

### Created And Coded By:
<a href = "https://github.com/hacker-404-error">Pritam Das</a>

<a href="https://github.com/hacker-404-error"><img src="https://i.ibb.co/yYd2Xjb/In-Shot-20220309-143908060.png" alt="Avatar" style="border-radius: 50%; width:70px"></a>



## 🔗 Feedback 
If you have any feedback, please reach out to me at [![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/pritam-das-7489ab223/)
