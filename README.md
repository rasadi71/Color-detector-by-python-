# 🎨 Real-Time Color Detection using OpenCV

This Python project uses **OpenCV** and **NumPy** to detect and track multiple colors (Red, Green, Yellow) in real time from a webcam feed.  
It identifies objects based on their color ranges in the HSV color space and draws bounding boxes with labels around the detected regions.

---

## 🧠 How It Works

1. The webcam captures live video frames.
2. Each frame is converted from **BGR to HSV** (Hue, Saturation, Value) color format — more effective for color detection.
3. Defined HSV color ranges for red, green, and yellow.
4. For each color:
   - A mask is created using `cv2.inRange()`.
   - Contours are detected with `cv2.findContours()`.
   - The largest contour (area > 500) is identified to avoid noise.
   - A bounding rectangle and text label are drawn around the detected object.

---

## 🧩 Supported Colors

| Color  | HSV Lower Bound | HSV Upper Bound | Display Color (BGR) |
|:-------|:----------------|:----------------|:--------------------|
| Red    | `[0, 120, 70]`  | `[10, 255, 255]` | `(0, 0, 255)` |
| Green  | `[40, 40, 40]`  | `[80, 255, 255]` | `(0, 255, 0)` |
| Yellow | `[20, 100, 100]`| `[30, 255, 255]` | `(0, 255, 255)` |

---

## ⚙️ Requirements

Make sure you have the following installed:

```bash
pip install opencv-python numpy
---
▶️ Usage

Save the code as color_tracker.py

Connect your webcam

Run the program:

python color_tracker.py


Press q to exit.
---

## 💡 Tip: If your webcam doesn’t open, change the camera index in the code:

cap = cv2.VideoCapture(0)
---
## 🧰 Code Explanation
Function	Description
cv2.VideoCapture()	Accesses the webcam feed
cv2.cvtColor()	Converts BGR → HSV color format
cv2.inRange()	Creates a mask for color filtering
cv2.findContours()	Detects contours (object boundaries)
cv2.rectangle()	Draws bounding boxes
cv2.putText()	Displays text labels
cv2.imshow()	Shows live video window
---
## 📸 Example Output

🟥 Red object → Red rectangle
🟩 Green object → Green rectangle
🟨 Yellow object → Yellow rectangle

Objects smaller than a threshold area are ignored to reduce noise.
---

## 🧪 Future Improvements

🚀 Add more colors (blue, orange, etc.)
🎯 Improve detection using morphology filters
🤖 Integrate with robotics for color-based control
---

## 🧑‍💻 Author

R.A.Sadi
🎥 YouTube:   U.robotics

💬 Exploring AI, Arduino, and Drones
