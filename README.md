# 🧠 Small Object Detection in Indoor Environments

This repository contains the official models and notebooks for the Final Year Project (FYP) titled **"Small Object Detection in Indoor Environments"**.  
The project explores the performance of **YOLOv8** and **YOLOv11** models with various activation functions for detecting small, everyday objects.

---

## 🧩 1. Project Overview

Detecting small objects in indoor environments is challenging due to **low resolution**, **cluttered backgrounds**, and **inconsistent lighting conditions**.  
This project aims to address these challenges by:

- Creating a **custom dataset** of small indoor objects.
- Implementing and training **state-of-the-art YOLOv8 and YOLOv11** models.
- Conducting a **comparative analysis of activation functions** — *SiLU, ReLU, ELU, LeakyReLU,* and *Sigmoid* — to observe their impact on detection performance.

📊 **Key finding:**  
The **YOLOv8 model with the ELU activation function** achieved the highest overall detection accuracy.

---

## 🗂️ 2. Dataset

A **custom dataset** was created using Roboflow, consisting of **10 small indoor object classes**:

| No. | Class Name  |
|:---:|:-------------|
| 1 | Battery |
| 2 | Cube |
| 3 | Cylinder |
| 4 | Dice |
| 5 | Eraser |
| 6 | Hexagon |
| 7 | Lego *(small block, difficult to detect)* |
| 8 | Marble |
| 9 | Paperclip |
| 10 | Screw |

### 🧾 Dataset Details
- **Source:** Roboflow  
- **Preprocessing:** Image resizing to `640x640`  
- **Augmentation Techniques:**  
  - Horizontal and vertical flips  
  - Random rotation between -15° and +15°  
  - 90° rotation for orientation diversity  

---

## ⚙️ 3. Models and Experiments

The experiments were conducted on two architectures — **YOLOv8s** and **YOLOv11s** — using five different activation functions.

### 🧪 Models Tested
- YOLOv8s  
- YOLOv11s  

### 🔬 Experiments Conducted
| Model | Activation Function | Description |
|:------|:--------------------|:-------------|
| YOLOv8 | SiLU *(Default)* | Baseline model |
| YOLOv8 | ReLU | Simple non-linear activation |
| YOLOv8 | LeakyReLU | Allows minor gradient flow for negative values |
| YOLOv8 | **ELU (Best Performer)** | Smooth and efficient gradient handling |
| YOLOv8 | Sigmoid | Bounded activation with limited performance |
| YOLOv11 | SiLU *(Default)* | Used as benchmark comparison |

Each model was trained for **50 epochs** with the same dataset split.

---

## 🧰 4. Repository Structure

```plaintext
Small-Object-Detection/
│
├── YOLOv8-ELU/
│   ├── best.pt
│   ├── test.ipynb
│
├── YOLOv8-ReLU/
│   ├── best.pt
│   ├── test.ipynb
│
├── YOLOv8-LeakyReLU/
│   ├── best.pt
│   ├── test.ipynb
│
├── YOLOv8-Sigmoid/
│   ├── best.pt
│   ├── test.ipynb
│
├── YOLOv11/
│   ├── best.pt
│   ├── test.ipynb
│
└── README.md
