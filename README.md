# 🎯 CodeAlpha - Object Detection and Tracking

Real-time object detection and multi-object tracking system built as part of the **CodeAlpha Artificial Intelligence Internship** (Task 4).

This project uses **YOLOv8** for real-time object detection and **ByteTrack** for multi-object tracking, allowing each detected object to be assigned and followed with a unique, persistent ID across video frames.

---

## 📌 Overview

The goal of this project is to detect and track multiple objects in a video stream in real time. Every object detected in the frame is:
- Localized with a bounding box
- Classified (person, car, dog, etc.)
- Assigned a unique tracking ID that stays consistent as the object moves across frames

This mirrors real-world use cases like surveillance systems, traffic monitoring, and people-counting applications.

---

## ✨ Features

- ✅ Real-time object detection using YOLOv8 (pre-trained on COCO dataset, 80 object classes)
- ✅ Multi-object tracking with persistent IDs using ByteTrack
- ✅ Clean, color-coded bounding boxes per object class
- ✅ Filled label backgrounds for better readability
- ✅ Live "Objects Tracked" counter overlay
- ✅ Works with both video files and live webcam input
- ✅ Output video automatically converted to MP4 (H.264) for universal playback

---

## 🛠️ Tech Stack

| Component | Technology |
|---|---|
| Detection Model | YOLOv8 (Ultralytics) |
| Tracking Algorithm | ByteTrack |
| Video Processing | OpenCV |
| Video Conversion | FFmpeg |
| Language | Python 3 |
| Environment | Google Colab (GPU) |

---

## 📂 Project Structure

CodeAlpha_ObjectDetectionTracking/
├── object_detection_tracking.ipynb   # Main Colab notebook (detection + tracking pipeline)
├── main.py                           # Local webcam version entry point
├── detector.py                       # YOLOv8 model wrapper
├── config.py                         # Project configuration/settings
├── requirements.txt                  # Python dependencies
├── demo/
│   └── output_final.mp4              # Sample output with detection + tracking
└── README.md
---

## 🚀 How It Works

1. **Input**: A video file (or webcam feed) is loaded frame by frame using OpenCV.
2. **Detection**: Each frame is passed to the YOLOv8 model, which detects objects and returns bounding boxes, class labels, and confidence scores.
3. **Tracking**: ByteTrack assigns a unique ID to each detected object and maintains that ID across frames, even through brief occlusions.
4. **Visualization**: Bounding boxes, class labels, and tracking IDs are drawn on each frame, along with a live counter of currently tracked objects.
5. **Output**: Processed frames are compiled into an output video, which is then converted to MP4 for compatibility.

---

## ▶️ How to Run

### Option 1: Google Colab (Recommended — no local setup needed)

1. Open `object_detection_tracking.ipynb` in Google Colab
2. Run the setup cell to install dependencies:
```python
   !pip install ultralytics -q
```
3. Upload your input video when prompted
4. Run all cells — the notebook will process the video and generate a tracked output video
5. Download the final MP4 from the last cell

### Option 2: Local Machine (Webcam)

```bash
git clone https://github.com/shehroz53531/CodeAlpha_ObjectDetectionTracking.git
cd CodeAlpha_ObjectDetectionTracking
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python main.py
```
Press `q` to quit the live detection window.

---

## 🎥 Demo

A sample output video showing detection and tracking in action is available in the `demo/` folder.

*(Also posted on LinkedIn — [link])*

---

## 📊 Model Details

- **Model used**: YOLOv8n (nano) — lightweight version optimized for speed
- **Dataset**: Pre-trained on the COCO dataset (80 common object classes: person, car, bicycle, dog, etc.)
- **Tracker**: ByteTrack, configured via `bytetrack.yaml`

---

## 🔮 Possible Improvements

- Add object counting/crossing-line logic for traffic or footfall analysis
- Support for custom-trained YOLO models on domain-specific objects
- Deploy as a web app using Streamlit or Flask for browser-based demos

---

## 👤 Author

**Shahroz Khalid**
CodeAlpha Artificial Intelligence Internship — Task 4
[GitHub](https://github.com/shehroz53531) | 

---

## 🙏 Acknowledgements

- [CodeAlpha](https://www.codealpha.tech) for the internship opportunity and task guidelines
- [Ultralytics](https://github.com/ultralytics/ultralytics) for the YOLOv8 model and tracking integration
