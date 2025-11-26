# 🚀 Bottle Cap Color Detection — Real-Time Computer Vision System

This repository contains a real-time computer vision project for detecting **bottle caps** and classifying them into **three colors**:

* **Light Blue**
* **Dark Blue**
* **Other Colors**

The dataset consists of images with bounding box annotations in **YOLO format**, but the original labels do not include color information.
As part of this project, bounding boxes are **manually re-labeled** according to the color of each cap.

This project focuses on:

* Model development & experimentation
* End-to-end explanation via Jupyter Notebook
* Analysis of model performance, dataset quality, and potential biases

> ⚠️ **Note**: This repository only covers **Task 1** (model development & experimentation).
> The ML pipeline (Task 2) is not implemented.
> I don't have much exposure to ML pipeline previously, but I've tried to learn the terms and tools. Unfortunately, I'm running out of time at the end.

Here is the code I used for my thesis research about Federated learning in the Predictive Maintenance domain. It is forecasting machine failure with time series data.
https://github.com/syarifhanan/Federated-Learning-PdM

---

# 📌 Project Overview

### 🎯 Objective

Build an object detection and color classification model capable of identifying bottle caps in images and categorizing their colors into **3 classes**. The approach aims for efficiency suitable for **real-time** applications.

### 🧠 Key Steps

1. **Dataset Understanding**

   * YOLO bounding box annotations provided with the dataset
   * Manual label adjustment based on cap color (light blue, dark blue, other)

2. **Model Choice**

   * Using **YOLO11** as the base model (Ultralytics latest YOLO)
   * Selected for speed + accuracy

3. **Training & Evaluation**

   * Training directly on annotated dataset
   * Evaluation using mAP metrics

4. **Insights & Analysis**

   * Model bias and failure cases
   * Discussion of real-time performance considerations

All experiment results and explanations are documented in the notebook.

---

# 📁 Repository Structure

```
.
│
├── main.ipynb                    # Model development using YOLO11s
│
├── main2.ipynb                   # Model development using YOLO11n
│
├── dataset/                      # Images & YOLO labels
│
├── runs/                         # YOLO training results
│
├── README.md                     # This file
└── requirements.txt              # Dependencies (optional)
```

---

# 🛠️ Set up & Installation

### 1. Create a virtual environment

install new venv using anaconda

### 2. Install dependencies

install Ultralytics YOLO manually:

```bash
pip install ultralytics
```

---

### 3. Labeling

label the images annotation manually with dark_blue, light_blue, and others


# 🧪 Usage

### Training YOLO11s and Inference

train and inference model using main.ipynb file

### Visualize results

YOLO automatically saves predictions under:

```
runs/detect/predict/
```

---

# 📊 Results

### ✔️ Model Used: `YOLO11s`

### ✔️ Input Size: *640*

### ✔️ Dataset Size: *12 image*

| Metric    | Score       | 
| --------- | ----------- |
| mAP50     | *0.992* |
| mAP50-95  | *0.61* |

### 📈 Performance Observations

On validating:
Speed: 0.3ms preprocess, 5.7ms inference, 0.0ms loss, 5.6ms postprocess per image

On separate inference:
Speed: 2.8ms preprocess, 23.3ms inference, 1.7ms postprocess per image at shape (1, 3, 640, 544)


---

# 🔍 Insights & Discussion


### ✔ Dataset Quality

* Limited dataset amount

### ✔ Model Bias

* Trained with YOLO11n shows poor detection result (fail to detect bottlecap), so model used is YOLO11s (not optimized for edge deployment)

### ✔ Limitations

* No real-time testing on a Raspberry Pi


---

# 🤝 Acknowledgements

* YOLO11 (Ultralytics)
* Dataset provided in the problem statement
