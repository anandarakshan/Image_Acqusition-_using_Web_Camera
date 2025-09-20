# EX 02: Image_Acqusition-_using_Web_Camera
## Name:Ananda Rakshan K V
## Reg.No:212223230014
## Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera.
### Step 2:
Use cv2.imread to read the video or image.
### Step 3:
Use cv2.imwrite to save the image.
### Step 4:
Use cv2.imshow to show the video.
### Step 5:
End the program and close the output video window by pressing 'q'.
## Program:
``` Python
### Developed By:Ananda Rakshan K V
### Register No:212223230014

## i) Write the frame as JPG file
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()
captured_image = cv2.imread('captured_frame.jpg')
plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
## ii) Display the video
cap = cv2.VideoCapture(0)
for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)
cap.release()
## iii) Display the video by resizing the window
cap = cv2.VideoCapture(0)
for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)
cap.release()
## iv) Rotate and display the video
cap = cv2.VideoCapture(0)
for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)
cap.release()
```
## Output

### i) Write the frame as JPG image
![alt text](<Screenshot 2025-09-12 172413.png>)
### ii) Display the video
![alt text](<Screenshot 2025-09-12 172511.png>)
### iii) Display the video by resizing the window
![alt text](<Screenshot 2025-09-12 172539.png>)
### iv) Rotate and display the video
![alt text](<Screenshot 2025-09-12 172606.png>)
## Result:
Thus the image is accessed from webcamera and displayed using openCV.
