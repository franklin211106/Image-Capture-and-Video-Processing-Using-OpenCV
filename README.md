# Image Capture and Video Processing Using OpenCV

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

## Program Developed By

**Name:** FRANKLIN .F

**Register No:** 212224240041

## Ex. No. 02

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

<img width="631" height="481" alt="image" src="https://github.com/user-attachments/assets/ff70bf48-5cd9-4382-b377-89656e388be0" />


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

<img width="626" height="485" alt="image" src="https://github.com/user-attachments/assets/45d6cbc9-ba64-497c-8086-3ad9e60dd495" />


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
<img width="322" height="467" alt="image" src="https://github.com/user-attachments/assets/3a849071-367f-474d-8d30-5ee448d84275" />


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

<img width="347" height="457" alt="image" src="https://github.com/user-attachments/assets/ae84a303-7a4c-4f82-b26c-f9ce0c2861be" />


---

## RESULT

Thus, the image was successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating were performed successfully using Python and OpenCV.
