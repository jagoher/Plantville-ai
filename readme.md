# 🌿 Plantville AI 

> Hybrid computer vision pipeline for tomato leaf disease detection using **YOLOv8** and **MobileNetV2**.
>
<img width="372" height="457" alt="image" src="https://github.com/user-attachments/assets/421294ed-894a-4e59-b1c3-3d5bd0f6c3e6" />


<p align="center">
  <img src="assets/demo_camera.jpg" width="700">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.11-blue.svg">
  <img src="https://img.shields.io/badge/TensorFlow-2.x-orange.svg">
  <img src="https://img.shields.io/badge/YOLOv8-Ultralytics-green.svg">
  <img src="https://img.shields.io/badge/Gradio-WebApp-red.svg">
  <img src="https://img.shields.io/badge/License-MIT-lightgrey.svg">
</p>

---

# 📖 Overview

Plantville AI is a hybrid computer vision system designed to detect tomato leaves and classify plant diseases under real-world conditions.

Instead of directly classifying the whole image, the project separates the problem into two stages:

1. **YOLOv8** detects the leaf.
2. **MobileNetV2** classifies the cropped leaf.

This approach reduces background noise and improves robustness in real environments.

---

# 🚀 Features

- 🌿 Automatic tomato leaf detection
- 🎯 YOLOv8 object detector
- 🧠 MobileNetV2 disease classifier
- 📷 Webcam support
- 🖼 Image upload
- ⚡ Real-time inference
- 📊 Confidence scores
- 🖥 Interactive Gradio interface

---

# 🏗 System Architecture

<p align="center">
  <img src="assets/architecture.png" width="800">
</p>

Pipeline:

```text
Image / Webcam
        │
        ▼
 YOLOv8 Detection
        │
        ▼
 Automatic Crop
        │
        ▼
 MobileNetV2 Classification
        │
        ▼
 Disease Prediction
```

The detector isolates the leaf before classification, allowing the classifier to focus only on the relevant region.

---

# 📂 Dataset

The project combines different datasets and training stages.

### Training

- PlantVillage Dataset
- Three disease classes

```
Tomato_blight
Tomato_healthy
Tomato_spot_or_virus
```

### Real-world inference

- Webcam images
- Real photographs
- YOLO-generated crops

---

# 📈 Results

| Model | Metric | Result |
|---------|---------|---------:|
| CNN (baseline) | Accuracy | **70.73%** |
| MobileNetV2 (PlantVillage) | Validation Accuracy | **94.53%** |
| YOLOv8 Detector | mAP50 | **99.5%** |
| MobileNetV2 (YOLO Crops) | Validation Accuracy | **85.99%** |

The hybrid pipeline provides the best balance between accuracy and robustness for real-world scenarios. :contentReference[oaicite:0]{index=0}

---

# 🎯 Detection Example

<p align="center">
  <img src="assets/demo_camera.jpg" width="650">
</p>

YOLO detects the tomato leaf and extracts the region of interest before disease classification.

---

# 📊 Confusion Matrix

<p align="center">
  <img src="assets/confusion_matrix.png" width="650">
</p>

Main observations:

- Healthy leaves are classified with high accuracy.
- Blight detection is highly reliable.
- Most errors occur between visually similar diseases such as:

```
Tomato_spot_or_virus
Tomato_blight
```

---

# 🖥 Gradio Demo

The application includes an interactive web interface.

Features:

- Webcam capture
- Image upload
- YOLO confidence threshold
- Bounding boxes
- Disease prediction
- Confidence score
- Prediction summary

<p align="center">
  <img src="assets/gradio_interface.png" width="750">
</p>

---

# 🛠 Technologies

- Python
- TensorFlow
- Keras
- MobileNetV2
- Ultralytics YOLOv8
- OpenCV
- NumPy
- Pandas
- Gradio

---

# 📁 Repository Structure

```text
plantville-ai/
│
├── app.py
├── README.md
├── requirements.txt
├── LICENSE
├── .gitignore
│
├── assets/
├── docs/
├── models/
├── notebooks/
├── results/
│
└── src/
    ├── config.py
    ├── models.py
    ├── detector.py
    ├── classifier.py
    ├── pipeline.py
    └── utils.py
```

---

# ⚙ Installation

Clone the repository

```bash
git clone https://github.com/jagoher/plantville-ai.git
cd plantville-ai
```

Create a virtual environment

```bash
python -m venv .venv
```

Activate it

Windows

```powershell
.\.venv\Scripts\activate
```

Linux

```bash
source .venv/bin/activate
```

Install dependencies

```bash
pip install -r requirements.txt
```

---

# 📦 Models

Due to GitHub file size limitations, trained models are not included.

Place the following files inside:

```text
models/
│
├── best.pt
└── mobilenetv2_yolo_crops_best.keras
```

---

# ▶ Run

```bash
python app.py
```

The Gradio interface will automatically open in your browser.

---

# 🔮 Future Work

- Support more crop species
- Add additional plant diseases
- Improve real-world dataset
- Full backbone fine-tuning
- Edge deployment (Jetson / Raspberry Pi)
- Model optimization for faster inference

---

# 👨‍💻 Author

**Jon Gorritxo**

Artificial Intelligence & Computer Vision Project

Hybrid pipeline based on **YOLOv8** and **MobileNetV2** for automatic plant disease detection.
