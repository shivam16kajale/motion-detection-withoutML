# 🎥 Motion Detection with OpenCV — No ML, Just Classic CV

This project demonstrates **real-time motion detection** using only traditional computer vision techniques in OpenCV. No machine learning. No deep learning. Just smart image processing.

## 🧠 Why This Project?

While modern computer vision often leans heavily on AI and machine learning, this project proves how effective **classical methods** can be for tasks like motion detection—especially when speed and simplicity matter.

## 🚀 Features

- Real-time motion tracking from a video file
- Frame differencing to detect movement
- Image preprocessing with:
  - Grayscale conversion
  - Gaussian blur
  - Canny edge detection
- Contour detection for identifying moving objects
- Bounding boxes drawn around detected motion
- Lightweight and easy to run

## 🛠️ How It Works

1. **Load Video:** Reads two consecutive frames from a video file.
2. **Detect Motion:** Compares the frames using `cv2.absdiff` to find differences.
3. **Preprocess Image:**
   - Converts to grayscale
   - Applies Gaussian Blur
   - Uses Canny edge detection to find edges
4. **Enhance and Extract Movement:**
   - Dilates the edges to make contours more visible
   - Finds contours and filters out small movements
5. **Draw Bounding Boxes:** Highlights moving objects in green boxes.

## 📦 Requirements

- Python 3.x
- OpenCV (`pip install opencv-python`)

## 📄 Code Example

```python
import cv2

vid = cv2.VideoCapture(r"C:\path\to\your\video.mp4")

s, f1 = vid.read()
s, f2 = vid.read()

while True:
    frame = cv2.absdiff(f1, f2)
    gray = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)
    blur = cv2.GaussianBlur(gray, (7, 7), 1)
    canny = cv2.Canny(blur, 30, 70)
    dil
