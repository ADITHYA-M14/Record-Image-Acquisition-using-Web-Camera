# Image Capture and Video Processing Using OpenCV

---

## Aim

To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

1. Write the frame as a JPG file  
2. Display the video  
3. Display the video by resizing the window  
4. Rotate and display the video  

---

## 🛠️ Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  

---

## ⚙️ Algorithm

### Step 1:
Import the required libraries and initialize the webcam using `cv2.VideoCapture()`.

### Step 2:
Capture frames continuously from the webcam.

### Step 3:
Save a frame as a JPG image using `cv2.imwrite()`.

### Step 4:
Display the live video stream using `cv2.imshow()`.

### Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

---

## 💻 Program


____________________________  

---

## Output

### i) Write the frame as JPG image
Captured image is saved as `captured_image.jpg`
```
import cv2
import matplotlib.pyplot as plt

cap = cv2.VideoCapture(0)

ret, frame = cap.read()

if ret:
    frame = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    plt.imshow(frame)
    plt.axis("off")
    plt.show()

cap.release()
```
<img width="512" height="410" alt="image" src="https://github.com/user-attachments/assets/402a049b-b0eb-4845-b1ad-61fa80195df7" />


### ii) Display the video
Live webcam video is displayed
```
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
<img width="512" height="389" alt="image" src="https://github.com/user-attachments/assets/fbcb7304-fb13-4ec9-a438-9612c7629212" />




### iii) Display the video by resizing the window
Video is shown in resized resolution (640 × 480)
```
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

    
    resized_frame = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(resized_frame)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```
<img width="266" height="389" alt="image" src="https://github.com/user-attachments/assets/dc3c36a6-6c52-4896-9b37-765d7f880013" />

### iv) Rotate and display the video
Video is displayed after rotation (90° clockwise)
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time

cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()

    if not ret:
        break

    
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)

    
    rotated_frame = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)

    clear_output(wait=True)
    plt.imshow(rotated_frame)
    plt.axis("off")
    plt.show()

    time.sleep(0.05)

cap.release()
```
<img width="297" height="389" alt="image" src="https://github.com/user-attachments/assets/a0526f3f-6bc7-4b56-83b2-7174be145c0a" />


---

## Result

Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.
