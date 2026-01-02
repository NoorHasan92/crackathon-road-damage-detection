# crackathon-road-damage-detection
# AI-Based Road Damage Detection using YOLOv8

This project was developed for **Crackathon**, organized by **IIT Bombay**.  
It focuses on automated detection and classification of road surface damages using deep learning–based object detection.

---

## 📌 Problem Statement
Manual inspection of road infrastructure is time-consuming, costly, and subjective.  
The goal of this project is to build an AI system that can automatically detect and classify different types of road damage from images, enabling faster and more scalable road condition assessment.

---

## 🧠 Model Architecture
- **Model:** YOLOv8s (single-stage object detector)
- **Framework:** PyTorch (Ultralytics YOLOv8)
- **Detection Type:** Anchor-free object detection
- **Backbone:** CSP-based feature extractor
- **Neck:** PAN-FPN for multi-scale feature aggregation
- **Head:** Decoupled classification and bounding box regression head

YOLOv8s was selected to balance detection accuracy and computational efficiency.

---

## 📂 Dataset
- **Dataset:** Road Damage Detection 2022 (RDD2022)
- **Total Images:** ~47,000
- **Annotation Format:** YOLO
- **Classes:**
  - Longitudinal Crack
  - Transverse Crack
  - Alligator Crack
  - Pothole
  - Other Corruption

Dataset configuration is provided in `data.yaml`.

---

## 🏋️ Training Strategy
- Pre-trained weights used for faster convergence
- Image size: **640 × 640**
- Epochs: **40**
- Optimizer: **AdamW**

### Data Augmentation Techniques:
- Mosaic augmentation
- Random horizontal flipping
- HSV color augmentation
- Random scaling and translation

These techniques improved generalization and reduced overfitting.

---

## 📊 Evaluation Results
Validation performance of the trained model:

- **mAP@50:** 0.589  
- **mAP@50–95:** 0.315  

The model performs particularly well on crack-type damages, while potholes remain more challenging due to shape and scale variations.

---

## 🚀 Improvements Over Baseline
- Use of YOLOv8 instead of older detection models
- Initialization with pre-trained weights
- Extensive data augmentation
- Hyperparameter tuning for stable convergence
- Best checkpoint selection based on validation mAP

---

## 📁 Repository Contents
- **`yolov8s.pt`** — Trained YOLOv8 model
- **`data.yaml`** — Dataset configuration file
- **`submission.zip`** — Generated prediction label files (`.txt`)
- **`README.md`** — Project documentation

> **Note:** Prediction images are omitted due to repository size limits.  
> Generated label (`.txt`) files are provided in `submission.zip`.

---

## 👤 Author
**Md Noor Hasan Ansari**  
B.Tech CSE Student  
Aliah University  

---

## 🏁 Conclusion
This project demonstrates the effectiveness of modern deep learning–based object detection for automated road damage assessment.  
The YOLOv8-based approach achieves strong performance while remaining efficient, making it suitable for real-world infrastructure monitoring applications.
