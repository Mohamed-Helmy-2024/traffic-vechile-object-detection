# Traffic Vehicle Detection System (YOLOv8n)

## Overview

This project implements a traffic vehicle detection system using the YOLOv8n model. It detects multiple types of vehicles and number plates from images and videos with real-time performance.

The system is built using Python and PyTorch and deployed through Gradio to provide an interactive web interface.

---

## Dataset

The dataset is sourced from Kaggle and contains labeled traffic scene images in YOLO format.

### Characteristics

* Annotation format: YOLOv5
* Data type: Images with bounding boxes
* Size: ~2000+ labeled samples
* Classes:

  * Car
  * Bus
  * Truck
  * Auto
  * Two Wheeler
  * Number Plate
  * Blur Number Plate

### Preparation

* Frames extracted from traffic videos using OpenCV
* Manual annotation using LabelImg
* Directory structure:

  ```
  images/
  labels/
  ```

---

## Model

* Model: YOLOv8n
* Framework: PyTorch
* Weights file: `best.pt`
* Task: Object Detection

### Features

* Real-time detection
* Multi-object detection
* Works on both images and videos
* Detects vehicles and license plates

---

## Technologies

### Programming Language

* Python

### Libraries

* ultralytics
* opencv-python
* numpy

### Tools

* LabelImg
* Kaggle
* Gradio

---

## Project Structure

```
.
├── YOLO_Traffic_Detection.ipynb
├── best.pt
├── OIP.webp
├── Vehicle Dataset Sample.mp4
├── README.md
```

---

## Installation

### Requirements

* Python 3.x
* pip

### Install Dependencies

```bash
pip install ultralytics opencv-python gradio
```

---

## Usage

### Run on Image

```python
from ultralytics import YOLO

model = YOLO("best.pt")
results = model("image.jpg", show=True)
```

### Run on Video

```python
results = model("video.mp4", show=True)
```

---

## Deployment (Gradio)

```python
import gradio as gr
from ultralytics import YOLO

model = YOLO("best.pt")

def detect(image):
    results = model(image)
    return results[0].plot()

app = gr.Interface(fn=detect, inputs="image", outputs="image")
app.launch()
```

---

## Results

The model successfully detects:

* Vehicles (car, bus, truck, etc.)
* Number plates

It provides bounding boxes around detected objects for both images and videos.

---

## Notes

* Avoid uploading large datasets to GitHub
* Use `.gitignore` to exclude unnecessary files
* Keep sensitive files outside the repository

---

## Future Work

* Improve detection accuracy
* Add webcam real-time detection
* Optimize model performance
* Enhance Gradio interface

---

## Author

Mohamed Helmy


