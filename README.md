

# FireScope: Real-Time Smoke & Fire Detection with YOLO11

### Problem Description

Fire incidents can cause catastrophic damage and loss of life when not detected early enough. Current detection methods, which rely primarily on traditional sensors, often have delayed response times that can lead to severe consequences. This creates a critical need for faster, more reliable detection systems that can identify fire hazards at their earliest stages. To address this challenge, this project implements advanced deep learning technology to detect fires and smoke as they emerge, enabling rapid response and intervention.

\

**Fire Scope** represents a state-of-the-art approach to fire safety monitoring. At its core, the system uses **YOLOv11**, a powerful object detection model, to continuously analyze video feeds for signs of fire and smoke in real-time. When potential threats are detected, the system immediately sends alerts through **Telegram/WhatsApp** messaging platforms, ensuring that stakeholders are notified without delay.

### Why Choose Fire Scope?

Key capabilities:
- Real-time video processing with 30-60 frames per second
- High-accuracy threat identification (80.6% Precision)
- Robust performance across various environmental conditions
- Immediate alert system with visual confirmation via Telegram and WhatsApp.
- Adaptable for multiple use cases including surveillance systems, industrial monitoring, home security, and robotic applications

The combination of speed, accuracy, and reliable notification makes Flare Guard particularly effective for environments where early fire detection is critical for safety and asset protection.


     
   ### 🔥 Fire Detection System in Action  
  This video demonstrates the system detecting fire immediately upon occurrence.  
  Alerts are sent instantly to **Telegram** and **WhatsApp**, including an attached image.  
  Thanks to **multithreading**, the system continues running without interruption.
  


## Dataset

The dataset consists of **10,463 annotated images**, available on [Roboflow](https://universe.roboflow.com/sayed-gamall/fire-smoke-detection-yolov11). This dataset is designed for training and evaluating **object detection models** tailored for real-time **fire and smoke detection**. It is suitable for:
* **Surveillance systems** (CCTV monitoring, smart security cameras)
* **Industrial safety applications** (factories, warehouses, refineries)
* **Residential safety solutions** (smart home fire detection)
* **Autonomous monitoring systems** (drones, robotics, IoT devices)

| Split      | Images | Annotations |
| ---------- | ------ | ----------- |
| Training   | 9,156  | 27,468      |
| Validation | 872    | 2,616       |
| Test       | 435    | 1,305       |

**Classes:** `Fire`, `Smoke`  
**Annotation Format:** YOLOv11-compatible bounding boxes

```python
# Download dataset via Roboflow
from roboflow import Roboflow
rf = Roboflow(api_key="YOUR_API_KEY")
project = rf.workspace("sayed-gamall").project("fire-smoke-detection-yolov11")
dataset = project.version(2).download("yolov11")
```

## Training Summary

The model was trained using **YOLOv11** on a dataset of fire and smoke images. Training stopped early due to no improvement over 20 epochs, with the best results observed at **Epoch 92**.


### Final Validation Results

| Metric        | Value     |
| ------------- | --------- |
| Precision (P) | **0.806** |
| Recall (R)    | **0.717** |
| mAP@50        | **0.770** |
| mAP@50-95     | **0.492** |

### Class-Specific Performance

| Class     | Precision | Recall | mAP@50 | mAP@50-95 |
| --------- | --------- | ------ | ------ | --------- |
| **Fire**  | 0.813     | 0.806  | 0.828  | 0.513     |
| **Smoke** | 0.800     | 0.629  | 0.711  | 0.472     |





