# Ex. No. 02 - Image Capture and Video Processing Using OpenCV
# Program Developed By
# Name:FRANKLIN .F
# Register No:212224240041


## AIM

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file.
2. Display the video.
3. Display the video by resizing the window.
4. Rotate and display the video.

## Software Required

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (`cv2`)
- Matplotlib

## Algorithm

### Step 1:
Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

### Step 2:
Capture frames continuously from the webcam.

### Step 3:
Save a frame as a JPG image using `cv2.imwrite()`.

### Step 4:
Display the live video stream using Matplotlib.

### Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.



## Output

### i) Write the frame as JPG image

Captured image is saved as `captured_image.jpg`.

**Program:**

```python
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)

ret, frame = cap.read()

if ret:
    cv2.imwrite("captured_image.jpg", frame)
    print("Image Saved Successfully")

cap.release()
```

**Output Screenshot:**

<img width="671" height="521" alt="image" src="https://github.com/user-attachments/assets/35fbab26-0bd3-4f96-a77e-b2f92ed69fff" />



---

### ii) Display the video

Live webcam video is displayed.

**Program:**

```python
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    frame = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(frame)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```

**Output Screenshot:**

<img width="636" height="480" alt="image" src="https://github.com/user-attachments/assets/733a9c6e-65a1-4044-95d4-7e6f658031ca" />



---

### iii) Display the video by resizing the window

Video is shown in resized resolution (640 × 480).

**Program:**

```python
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    resized_frame = cv2.resize(frame, (640, 480))

    resized_frame = cv2.cvtColor(
        resized_frame,
        cv2.COLOR_BGR2RGB
    )

    clear_output(wait=True)
    plt.imshow(resized_frame)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```

**Output Screenshot:**
<img width="328" height="467" alt="image" src="https://github.com/user-attachments/assets/79e2eef8-1e5c-4288-bc13-4d36af6d9311" />



---

### iv) Rotate and display the video

Video is displayed after rotation (90° clockwise).

**Program:**

```python
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    rotated_frame = cv2.rotate(
        frame,
        cv2.ROTATE_90_CLOCKWISE
    )

    rotated_frame = cv2.cvtColor(
        rotated_frame,
        cv2.COLOR_BGR2RGB
    )

    clear_output(wait=True)
    plt.imshow(rotated_frame)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```

**Output Screenshot:**

<img width="297" height="389" alt="download" src="https://github.com/user-attachments/assets/e541d9e8-b932-4d07-9b15-a07799a243d6" />



---

## RESULT

Thus, the image was successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating were performed successfully using Python and OpenCV.
