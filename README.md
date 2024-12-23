---

# Parking Spot Detection Project

## Overview

This parking spot detection project consists of a dataset folder, `main.py`, `util.py`, `requirements.txt`, and the trained model stored in `model.pkl`. Below is a breakdown of the project components and an explanation of the code and its functionality.

## Project Structure

### Dataset Folder

The dataset folder includes the following:

1. **Data**: Contains video footage (`parking_1920_1080_loop.mp4`) used for parking spot detection and a mask image (`mask_1920_1080.png`) that identifies parking spots in the frame.
2. **Graphs**: Includes visual results or performance metrics obtained from the trained classifier. These could be histograms, accuracy plots, or confusion matrices.

### First Script: Marking Parking Areas

This script allows users to draw and label parking spaces on a video frame. The drawn parking areas and their labels are saved for later use.

#### Key Steps:

1. **Video Capture Setup**: Initializes video capture using OpenCV to load a video that serves as the base for drawing and labeling parking spaces.
2. **Polylines and Area Names**: Loads or initializes lists for previously marked parking areas (polylines) and their labels from a pickle file.
3. **Drawing Function**: Allows users to draw polygons on the video frame with the mouse and label them.
4. **Displaying Polygons and Labels**: Overlays stored polygons and their names onto the video frames.
5. **Saving and Exiting**: Saves the drawn polygons and labels to a pickle file and allows the user to exit the program.

### Second Script: Detecting Cars in Marked Parking Areas

This script uses a pre-trained YOLO model to detect cars within the marked parking areas created with the first script.

#### Key Steps:

1. **Loading Pre-Defined Polylines**: Loads previously saved polygons and labels from a pickle file.
2. **Loading YOLO Model and Classes**: Loads a YOLO model for object detection and reads class names from a file.
3. **Processing Video Frames**: Analyzes every third frame for efficiency.
4. **Detecting Objects**: Uses YOLO to detect objects in the current frame and stores detected bounding boxes.
5. **Identifying Cars**: Filters bounding boxes to find cars and calculates their center coordinates.
6. **Checking Parking Areas**: Checks if the center of each detected car falls within any predefined polygons.
7. **Counting Cars and Free Spaces**: Calculates the total number of cars and free spaces, displaying the results on the video frame.
8. **Displaying Results**: Displays the updated frame with detected cars, polygons, and counts until the user exits.

### Usage Instructions

1. **Install Dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

2. **Run the First Script**:
   ```bash
   python main.py
   ```

3. **Run the Second Script**:
   ```bash
   python detect_cars.py
   ```

### Visual Results

Here you can include images, screenshots, and a short video showcasing the results of the parking spot detection system:

- **results 1: Detected Empty and Occupied Spots**
  
  ![Detected Spots](https://github.com/Micahmichael03/parking-space-using-YOLO11/blob/main/output_with_detections.mp4)

- **Video: Parking Spot Detection in Action**
  
  ![Parking Spot Detection Video](https://github.com/Micahmichael03/parking-space-using-YOLO11/blob/main/parking1.mp4)

### Contributing

Feel free to fork this project, make improvements, and submit pull requests. Contributions are welcome!

### License

This project is licensed under the MIT License. See the LICENSE file for more details.

### Contact

For any questions or inquiries, please contact the project maintainer at [makoflash05@gmail.com].

---
