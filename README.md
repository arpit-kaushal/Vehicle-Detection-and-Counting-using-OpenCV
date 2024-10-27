
# **Vehicle Detection and Counting using OpenCV**

This project demonstrates vehicle detection and counting using OpenCV and background subtraction. Vehicles are detected as they cross a predefined counting line in a video feed, making it suitable for applications like traffic monitoring and vehicle count analytics.


## Features

- **Background Subtraction:** Utilizes cv2.createBackgroundSubtractorMOG2 for motion-based object detection.
- **Vehicle Counting:** Counts vehicles crossing a specific line on the screen.
- **Contour Detection:** Detects vehicles based on their contours, bounding each with a rectangle.
- **Real-Time Display:** Shows real-time video feed with detected vehicles, count line, and total vehicle count displayed on the screen.


## Prerequisites

Ensure the following libraries are installed:

**pip install opencv-python-headless**
## How to Use

1. Add the Video File:
- Place the video file (e.g., video.mp4) in the same directory as the script.

2. Run the Script:
- Execute the Python script:    
    **python vehicle_counter.py**

3. Controls:
- The video feed window will display the original video with real-time vehicle detection.
- Press Enter to terminate the program.

## Code Overview

### Core Components

- Background Subtraction: Detects moving objects by subtracting the background.         
    
     **algo = cv2createBackgroundSubtractorMOG2()**

- Center Calculation: Determines the center of detected objects to track movement across the count line.

    **def center_handle(x, y, w, h):    
    cx = int(x + w / 2)     
    cy = int(y + h / 2)     
    return cx, cy**

- Counting Line: A fixed line at a specific position in the frame is used to count vehicles as they cross.

    **count_line_position = 550**

- Vehicle Detection: For each detected contour, validates the size to ensure it's a vehicle.

    **for (i, c) in enumerate(counterShape):      
        (x, y, w, h) = cv2.boundingRect(c)
        validate_counter = (w >= min_width_react) and (h >= min_height_react)   
        if not validate_counter:    
            continue**


## Real-Time Display

The script draws bounding boxes and the counting line in the real-time video feed window, as well as displays the vehicle count on the screen.
## Output

Each vehicle crossing the counting line increments the count, which is displayed in the terminal and on the video feed.