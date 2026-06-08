# chicken-count
A YOLOv8-based chicken detection and counting system that tracks unique chickens in video using ByteTrack.

---

## Features

- Detects and tracks chickens across video frames
- Assigns unique IDs 
- Line-crossing logic to prevent re-counting
- Live overlay showing current and total unique count
- Single image detection 
- Runs on Google Colab with Google Drive

---

## Results

![Demo](results/demo.gif)

---

## Setup

```bash
pip install ultralytics supervision opencv-python
```

Place your dataset in Google Drive:
```
MyDrive/ChickenCount/dataset/
├── train/images/
├── valid/images/
├── test/images/
└── data.yaml
```

Then open `ChickenCount.ipynb` in Google Colab and run the cells in order.

---

## How It Works

1. **Train** — YOLOv8s trained on your chicken dataset (50 epochs, 416×416)
2. **Video count** — ByteTrack assigns unique IDs; a vertical line prevents re-counting chickens that cross sides
3. **Image detect** — runs detection on a single image and draws bounding boxes with confidence scores

---

## Tech Stack

- [YOLOv8](https://github.com/ultralytics/ultralytics) — object detection
- [ByteTrack](https://github.com/roboflow/supervision) via Supervision — multi-object tracking
- OpenCV — video processing

---
