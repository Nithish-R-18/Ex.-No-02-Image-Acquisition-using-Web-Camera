# Image Acquisition Using Web Camera

*Name:* NITHISH R

*Register Number:* 212225230202 

*Experiment:* Image Handling and Pixel Transformations Using OpenCV

---

## Aim

To write a Python program using OpenCV to capture images from a webcam and perform the following image manipulations:

1. Write the captured frame as a JPG file.
2. Display the video.
3. Display the video by resizing the frame.
4. Rotate and display the video.

## Software Used

- Anaconda
- Python 3.7
- OpenCV
- NumPy

## Algorithm

### Step 1
Import the `cv2` and `numpy` packages.

### Step 2
Read the video frame using `cv2.VideoCapture(0)`.

### Step 3
Write the captured image using `cv2.imwrite()`.

### Step 4
Display the video frame using `cv2.imshow()`.

### Step 5
Divide the frame into four parts, resize the frame, and assign the smaller frame to each part.

### Step 6
Rotate the frame using `cv2.rotate()` and display the output.

## Program

**Developed By:** NITHISH R

**Register Number:** 212225230202

## i) Write the Frame as a JPG File

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
```

## ii) Display the Video

```python
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
```

## iii) Display the Video by Resizing the Frame

```python
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
```

## iv) Rotate and Display the Video

```python
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

### i) Write the Frame as a JPG Image


<img width="647" height="517" alt="Screenshot 2026-10-26 132418" src="https://github.com/user-attachments/assets/36ad58cb-3512-431b-976f-c05e84423aff" />


### ii) Display the Video


<img width="632" height="478" alt="Screenshot 2026-10-26 132737" src="https://github.com/user-attachments/assets/c7ab13b3-c907-45a3-8608-bbae0156fff2" />


### iii) Display the Video by Resizing the Frame


<img width="327" height="481" alt="Screenshot 2026-10-26 132846" src="https://github.com/user-attachments/assets/e4119cbb-bb7e-4898-b011-2ebca66b9f66" />


### iv) Rotate and Display the Video


<img width="357" height="476" alt="Screenshot 2026-10-26 132958" src="https://github.com/user-attachments/assets/ecb709b8-e6c2-4b55-b53f-b308f1c51aef" />


## Result

Thus, images were captured from the webcam, saved as JPG files, and displayed using OpenCV. The video frames were resized and rotated successfully.
