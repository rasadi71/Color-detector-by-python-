 Real-Time Multi-Color Object Tracker

A simple, real-time color tracking script built using Python and the OpenCV library. It uses the HSV (Hue, Saturation, Value) color space to reliably identify and track multiple colored objects from a live webcam feed.

✨ Features

Real-Time Detection: Processes video input from a webcam in real time.

Multi-Color Tracking: Simultaneously tracks distinct colors (Red, Green, Yellow) by default.

Visual Feedback: Draws bounding boxes and displays the color name label over the detected objects.

Configurable: Easy to adjust color ranges and camera index.

⚙️ Prerequisites

You must have Python 3.x installed on your system.

Dependencies

This project requires the following Python libraries:

OpenCV (cv2): For image processing and video capture.

NumPy: For efficient array manipulation (used for HSV masks).

💻 Installation and Setup

Clone the repository (or save the code as color_tracker.py).

Install the required libraries using pip:

pip install opencv-python numpy



🚀 How to Run

Check your Camera Index: By default, the script attempts to open camera index 1 (cv2.VideoCapture(1)).

If you are using a built-in laptop camera, you may need to change 1 to 0.

If you have multiple external cameras, you may need to try different indices (e.g., 2, 3).

Execute the script from your terminal:

python color_tracker.py



A window titled 'Color Tracker' will open, displaying the live feed with boxes drawn around the detected colors.

Press the 'q' key to gracefully stop the script and close the window.

🎨 Customization

The core logic for color detection is handled by the colors dictionary, which defines the HSV ranges for tracking.

Default Color Ranges

Name

Lower HSV Bound

Upper HSV Bound

Box Color (BGR)

Red

[0, 120, 70]

[10, 255, 255]

(0, 0, 255) (Red)

Green

[40, 40, 40]

[80, 255, 255]

(0, 255, 0) (Green)

Yellow

[20, 100, 100]

[30, 255, 255]

(0, 255, 255) (Yellow)

Modifying Ranges

You can edit the color_tracker.py file to adjust the sensitivity or add new colors:

HSV Values: The arrays define the min/max 

$$H, S, V$$

 values (Hue: 0-179, Saturation: 0-255, Value: 0-255).

Box Color: The tuple defines the BGR color for the bounding box.

# Example of the dictionary structure in the code:
colors = {
    # name: ([H_min, S_min, V_min], [H_max, S_max, V_max], (Box_B, Box_G, Box_R))
    "red":   ([0, 120, 70], [10, 255, 255], (0, 0, 255)),
    # Add a new color (e.g., blue):
    "blue":  ([100, 150, 0], [140, 255, 255], (255, 0, 0)),
}



Area Threshold

To filter out noise or very small objects, the script ignores any detected contour with an area less than 500. You can increase this value if you only want to track larger objects:

if cv2.contourArea(largest) > 500: # Change 500 to a higher value like 1500
    # ... draw rectangle



🛑 Stopping the Program

Press q on your keyboard while the 'Color Tracker' window is active.
