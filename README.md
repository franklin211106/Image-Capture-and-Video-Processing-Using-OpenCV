# EXP-2-Record-Image-Acquisition-using-Web-Camera

## Aim:
To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file

2. Display the video

3. Display the video by resizing the window

4. Rotate and display the video


## Software Used:

Anaconda – Python 3.7

Jupyter Notebook / VS Code

OpenCV (cv2)

## Algorithm:

Step 1:
Import the required libraries and initialize the webcam using cv2.VideoCapture().

Step 2:
Capture frames continuously from the webcam.

Step 3:
Save a frame as a JPG image using cv2.imwrite().

Step 4:
Display the live video stream using cv2.imshow().

Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

## Program:

### Developed By:
### Name: FRANKLIN F
### Reg.No: 212224240041

```python

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

## Output:

### i) Write the frame as JPG image
Captured image is saved as captured_image.jpg


<img width="512" height="410" alt="download" src="https://github.com/user-attachments/assets/015b9a35-ad60-498e-817c-91e2ddce6913" />



### ii) Display the video
Live webcam video is displayed

<img width="512" height="389" alt="download" src="https://github.com/user-attachments/assets/48fb81de-c904-4aae-8be9-eb72a2eda10b" />



### iii) Display the video by resizing the window
Video is shown in resized resolution (640 × 480)


<img width="306" height="457" alt="image" src="https://github.com/user-attachments/assets/a96a98c5-2756-444d-b63a-bb5df24f470d" />



### iv) Rotate and display the video
Video is displayed after rotation (90° clockwise)


<img width="342" height="457" alt="image" src="https://github.com/user-attachments/assets/8286c3b0-5cf4-4a22-af72-ec1dd21b9d92" />



## Result:

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
