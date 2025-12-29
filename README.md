# Hand Gesture Control Suite

A comprehensive hand gesture recognition and control system built with **MediaPipe** and **OpenCV**. This project demonstrates various real-world applications of computer vision for hands-free computer control.

## 🎯 Features

### 1. **Finger Counting Detection**
- Real-time finger counting (0-5 fingers)
- Left/right hand detection
- Visual feedback with hand landmark overlay

### 2. **Mouse Control**
- Control your mouse cursor with index finger movement
- Natural hand tracking for precise cursor control
- Screen coordinate mapping

### 3. **Volume Control**
- Control system volume by pinching thumb and index finger
- Multiple implementations:
  - Distance-based control
  - Angle-based control (wrist-thumb-index angle)
  - Normalized distance (perspective-corrected)
- Visual feedback with progress indicators

### 4. **Gesture-Based Navigation**
- **Swipe Up**: Open task view (Windows Task View)
- **Swipe Down**: Show desktop
- **Swipe Left**: Switch to previous app
- **Swipe Right**: Switch to next app

### 5. **Interactive UI**
- Button-based menu system
- Hover-to-click interaction (2-second hover)
- Toggle mouse control and virtual keyboard
- Progress circle visual feedback

### 6. **Pong Game**
- Hand-controlled Pong game
- Move paddle with hand position
- Real-time gameplay

## 📋 Requirements

```bash
mediapipe
opencv-python
pyautogui
pycaw
comtypes
numpy
```

## 🚀 Installation

1. Clone the repository:
```bash
git clone https://github.com/Ghorbel37/hand-gesture-control-suite.git
cd hand-gesture-control-suite
```

2. Install dependencies:
```bash
pip install mediapipe opencv-python pyautogui pycaw comtypes numpy
```

## 💻 Usage

### Running the Notebooks

The project contains two Jupyter notebooks:

- **`Hand detector Project.ipynb`**: Main implementation with all features
- **`Hand detector Project Experimental.ipynb`**: Experimental features and variations

To run:
```bash
jupyter notebook
```

Then open either notebook and run the cells sequentially.

### Individual Features

Each feature can be run independently by executing the corresponding code cell in the notebook:

1. **Finger Counting**: Run cells 0-2
2. **Mouse Control**: Run cells 3-5
3. **Volume Control**: Run cells 6-8 (or 9-12 for angle/normalized versions)
4. **Gesture Navigation**: Run cells 13-14
5. **Pong Game**: Run cells 15-16

## 🎮 Controls

### Finger Counting
- Show 1-5 fingers to the camera
- The system displays the count in real-time

### Mouse Control
- Raise your index finger to move the cursor
- Lower your finger to stop control

### Volume Control
- **Distance Method**: Pinch thumb and index finger closer to decrease volume, spread apart to increase
- **Angle Method**: Adjust the angle between wrist, thumb, and index finger
- Touching fingers together mutes the volume

### Gesture Navigation
- Make swiping motions with your index finger:
  - **Up**: Fast upward motion
  - **Down**: Fast downward motion
  - **Left/Right**: Fast horizontal motions

## 🔧 Technical Details

### Hand Landmark Detection
The project uses MediaPipe Hands solution with 21 hand landmarks:
- **Landmark 0**: Wrist
- **Landmark 4**: Thumb tip
- **Landmark 8**: Index finger tip
- **Landmark 12**: Middle finger tip
- **Landmarks 16, 20**: Ring and pinky tips

### Key Technologies
- **MediaPipe**: Google's framework for building perception pipelines
- **OpenCV**: Computer vision library for image processing
- **PyAutoGUI**: GUI automation for mouse/keyboard control
- **Pycaw**: Python Core Audio Windows Library for volume control

### Performance Optimizations
- Confidence thresholds: `min_detection_confidence=0.7`, `min_tracking_confidence=0.7`
- Image flipping for selfie-view (mirror effect)
- RGB/BGR color space conversions for optimal processing
- Frame-by-frame processing with efficient landmark detection

## 🎨 Project Structure

```
handtracking/
│
├── Hand detector Project.ipynb              # Main project notebook
├── Hand detector Project Experimental.ipynb # Experimental features
└── README.md                                # This file
```

## 🐛 Troubleshooting

### Camera Not Detected
- Ensure your webcam is properly connected
- Check if other applications are using the camera
- Try changing `cv2.VideoCapture(0)` to `cv2.VideoCapture(1)` for external cameras

### Volume Control Not Working
- Windows-specific: Ensure the `pycaw` library is properly installed
- Run as administrator if permission issues occur

### Poor Hand Detection
- Ensure good lighting conditions
- Keep hand within camera frame
- Adjust `min_detection_confidence` value (lower for easier detection)

### Gesture Recognition Issues
- Adjust `swipe_threshold` for sensitivity
- Modify `hover_duration` for button click timing
- Calibrate distance thresholds based on your camera resolution

## 📝 Notes

- **Platform**: Currently optimized for Windows (virtual keyboard, volume control)
- **Camera**: Requires a working webcam
- **Python Version**: Tested with Python 3.7+
- **Exit**: Press `ESC` key to close any running application

## 🎓 Educational Purpose

This project was developed as part of a Computer Vision course to demonstrate practical applications of hand landmark detection, gesture recognition algorithms and real-time computer vision processing

## 📄 License

This project is open-source and available for educational purposes.

## 🤝 Contributing

Feel free to fork this project and submit pull requests for improvements or new features!