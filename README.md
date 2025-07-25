# ASL Detection – Graduation Project

A **real-time American Sign Language (ASL) detector** that classifies static hand gestures into alphabet letters. This project combines **deep learning (CNNs)** and **feature-based approaches (Mediapipe landmarks + XGBoost)** to achieve high accuracy in both offline and real-time scenarios.

---

## Project Overview

The goal of this project was to **build a model capable of real-time ASL letter detection** from webcam input. It evolved from working with simple image classification (Sign Language MNIST) to robust real-world detection using **landmarks instead of raw pixels**.

---

## Datasets Used

### 1. **Sign Language MNIST**
- 28×28 grayscale images
- 27,455 training images and 7,172 test images
- Represents letters A–Y (excluding J and Z, which require motion)

### 2. **ASL Alphabet Dataset**
- 87,000 color images (RGB)
- 29 classes (A–Z + Space, Delete, Nothing)
- Real-world backgrounds and 200×200 resolution for better feature representation

---

## Approach

### **Phase 1 – CNN with Raw Pixels**
- Built 3-block CNN architecture (32→64→128 filters)
- Achieved **99% accuracy** on ASL Alphabet Dataset
- Real-time performance struggled due to background noise and dataset-specific patterns

### **Phase 2 – Landmark-Based Features with Mediapipe**
- Used Mediapipe to extract **21 key hand landmarks (x,y,z) = 63 features**
- Focused on hand geometry, removing unnecessary background data

### **Phase 3 – XGBoost Classifier**
- Trained XGBoost on 63 landmark features
- Achieved **99.19% real-time accuracy**
- Outperformed CNNs for structured/tabular feature input

---

## Tech Stack

- **Python**
- **TensorFlow / Keras**
- **Mediapipe** (hand landmark detection)
- **XGBoost**
- **OpenCV** (real-time webcam input)

---

## Future Work

- Support **dynamic gestures** (J, Z) using sequence models (LSTM/GRU).
- Improve **real-time UI/UX** (confidence scores, visual overlays).
- Deploy as a **web or mobile app**.

---

## Repository Structure

