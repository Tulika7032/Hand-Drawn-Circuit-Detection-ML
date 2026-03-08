# Hand-Drawn-Circuit-Detection-ML
Recognizing Hand-Drawn Circuit Components 

---

## Overview

This project focuses on detecting and classifying **hand-drawn circuit schematic components** using computer vision and deep learning techniques.

Circuit diagrams drawn on paper or whiteboards are common during learning and early design stages. Converting these sketches into structured digital representations require reliable symbol recognition.

This system experiments with multiple approaches to identify circuit components from images and compares their performance.

This project demonstrates:

- Preprocessing of noisy hand-drawn circuit images
- Template matching for basic symbol detection
- Feature-based detection using SIFT
- Circuit symbol classification using CNN
- Object detection using YOLO

---

## System Components

### 1. Image Preprocessing Module

The preprocessing module prepares raw circuit images before applying detection or classification algorithms.

#### Key Responsibilities

- Load input circuit images
- Convert images to grayscale
- Apply noise reduction filters
- Perform binary thresholding
- Resize images for model input

#### Major Features

- Bilateral filtering for noise removal
- Binary thresholding for clearer symbol edges
- Image resizing to standard dimensions (224×224)
- Improves symbol visibility for training and inference

---

### 2. Template Matching Module

This module detects circuit symbols using **OpenCV template matching**.

#### Key Responsibilities

- Compare input images with stored symbol templates
- Calculate similarity scores
- Identify the most similar symbol template

#### Major Features

- Simple implementation using OpenCV
- Fast execution
- Serves as a baseline approach for comparison

#### Limitations

- Sensitive to scale changes
- Sensitive to rotation
- Less robust for noisy hand-drawn images

---

### 3. SIFT Feature Matching Module

This module uses **Scale-Invariant Feature Transform (SIFT)** to detect circuit symbols based on feature matching.

#### Key Responsibilities

- Detect keypoints in input images
- Extract feature descriptors
- Match descriptors with stored symbol features

#### Major Features

- Handles scale changes better than template matching
- Detects distinctive features in circuit symbols
- More robust to slight variations in drawings

---

### 4. CNN Classification Module

The CNN module uses a **Convolutional Neural Network** to classify circuit symbols.

#### Key Responsibilities

- Train a neural network using labeled symbol images
- Learn spatial features of circuit components
- Predict the correct class for unseen images

#### Major Features

- Automatic feature extraction
- Higher accuracy compared to classical methods
- Handles moderate noise and distortions

#### Model Pipeline

1. Image preprocessing  
2. Dataset splitting (train / validation / test)  
3. CNN training  
4. Model evaluation  
5. Prediction on new images  

---

### 5. YOLO Object Detection Module

This module uses **Ultralytics YOLO** for detecting multiple circuit symbols within a single image.

#### Key Responsibilities

- Detect multiple circuit components in one image
- Generate bounding boxes around detected symbols
- Classify detected symbols

#### Major Features

- Real-time object detection
- High detection accuracy
- Supports multi-object detection

---


---

## Dataset

The project uses the **Hand-Drawn Circuit Schematic Components Dataset** from Kaggle.

### 🔗 Dataset Link
[Hand-Drawn Circuit Schematic Components](https://www.kaggle.com/datasets/moodrammer/handdrawn-circuit-schematic-components)

This dataset contains multiple hand-drawn circuit symbols used for training and evaluation.

Example symbols include:

- Resistor
- Capacitor
- Inductor
- Diode
- Transistor
- Ground
- Voltage Source

Each symbol class contains multiple variations of **hand-drawn samples** to simulate real-world sketches.

---

## Evaluation Metrics

The models are evaluated using the following metrics:

- Accuracy
- Precision
- Recall
- F1 Score
- Confusion Matrix

Visualization libraries used:

- Matplotlib
- Seaborn

---

## Technologies Used

- Python
- OpenCV
- PyTorch
- Ultralytics YOLO
- Albumentations
- Scikit-learn
- Matplotlib

---

## Running the Project

### Install Dependencies

```bash
pip install opencv-python-headless
pip install albumentations
pip install ultralytics
pip install torchmetrics
pip install opendatasets
```
