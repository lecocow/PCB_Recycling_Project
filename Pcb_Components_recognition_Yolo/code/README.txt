# YOLO PCB Detection & Training

This project contains notebooks, models, and a dataset related to the use and training of **YOLO (You Only Look Once)** for object detection, specifically applied to PCB recycling and other automation use cases.

## Table of Contents
- [Description](#description)
- [Repository Structure](#repository-structure)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
  - [1. Training](#1-training)
  - [2. Testing](#2-testing)
  - [3. Coordinate Extraction](#3-coordinate-extraction)
- [Dataset](#dataset)
- [Models Included](#models-included)
- [Contributing](#contributing)
- [License](#license)

---

## Description

The goal of this project is to provide tools for:
- **Training a YOLO model** on a custom annotated dataset.
- **Testing pre-trained models** on new PCB images.
- **Extracting object coordinates** for further integration into automated systems.

---

## Repository Structure

```
YOLO_PCB/
│
├── code/
│   └── Train_program.ipynb        # YOLO training notebook
│   └── Test_program.ipynb         # Testing and evaluation notebook
│   └── Coordinates_program.ipynb  # Coordinate extraction notebook
├── YOLO_models/
│   └──  yolo11m.pt                 # Base YOLO pre-trained model
│   └──  yolo11m_train.pt           # YOLO model trained on your dataset
├── Board_detect.v5i.yolov11.zip   # YOLO dataset for PCB detection
└── README.md                  # Project documentation
```

---

## Requirements

- Python 3.8+  
- [PyTorch](https://pytorch.org/)  
- [Ultralytics YOLO](https://github.com/ultralytics/ultralytics)  
- [OpenCV](https://opencv.org/)  
- [numpy](https://numpy.org/)  
- [matplotlib](https://matplotlib.org/)  

Install dependencies with:  
```bash
pip install ultralytics opencv-python numpy matplotlib
```

---

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/lecocow/PCB_Recycling_Project.git
    cd PCB_Recycling_Project
   ```

2. Install dependencies as listed in **Requirements**.

---

## Usage

### 1. Training

Run the notebook **`Train_program.ipynb`** to:
- Load a YOLO dataset.
- Train a model starting from `yolo11m.pt`.
- Save the trained model as `yolo11m_train.pt`.

Example with **Ultralytics YOLO**:
```bash
yolo detect train data=data/Board_detect.v5i.yolov11/data.yaml model=yolo11m.pt epochs=50 imgsz=640
```

---

### 2. Testing

Use **`Test_program.ipynb`** to:
- Load a model (`yolo11m.pt` or `yolo11m_train.pt`).
- Run inference on new images.
- Visualize detections with labels and confidence scores.

---

### 3. Coordinate Extraction

With **`Coordinates_program.ipynb`**, you can:
- Load a YOLO model.
- Extract bounding box coordinates (x, y, width, height).

---

## Dataset

The included dataset is:  

```
├── Board_detect.v5i.yolov11.zip   # YOLOv5/YOLOv11 dataset for PCB detection
```

### Dataset Content
- **images/**: training and validation images.  
- **labels/**: YOLO format annotations (`.txt`).  
- **data.yaml**: dataset configuration file.  

### Extraction
```bash
unzip data/Board_detect.v5i.yolov11.zip -d data/
```

Resulting structure:
```
data/
├── Board_detect.v5i.yolov11/
│   ├── train/
│   │   ├── images/
│   │   └── labels/
│   ├── valid/
│   │   ├── images/
│   │   └── labels/
│   └── data.yaml
```

---

## Models Included

- **`yolo11m.pt`**: generic pre-trained YOLO model.  
- **`yolo11m_train.pt`**: YOLO model fine-tuned on your dataset.  

---

## Contributing

Contributions are welcome!  
1. Fork the repository.  
2. Create a branch (`git checkout -b feature/my-feature`).  
3. Commit your changes (`git commit -m "Add new feature"`).  
4. Push to the branch (`git push origin feature/my-feature`).  
5. Open a Pull Request.  

---

