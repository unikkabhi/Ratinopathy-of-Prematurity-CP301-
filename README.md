# 🧠 Retinopathy of Prematurity (ROP) Detection using Deep Learning

This project uses **PyTorch** and **Transfer Learning** (ResNet18) to detect **Retinopathy of Prematurity (ROP)** from preprocessed retinal images. The model classifies eye images into one of three categories:  
- `NORMALROP`: Normal retina  
- `AROP1`: Aggressive ROP Type 1  
- `AROP2`: Aggressive ROP Type 2  

Additionally, a real-time inference script is provided for doctors or end users to make predictions using webcam-captured images or local image files.

---

## 📁 Dataset Structure

The dataset used is preprocessed and saved in `.npy` format for faster I/O and memory efficiency. The folder structure is:


---

## 🧪 Preprocessing

All original ROP retinal images were:
- Normalized and resized
- Converted to NumPy `.npy` arrays to reduce load time and storage overhead
- Expanded to RGB format for ResNet compatibility (from grayscale)

---

## 🏗️ Model Architecture

- **Base Model**: ResNet18 (Pretrained on ImageNet)
- **Modified Output Layer**: 3 neurons with Softmax activation
- **Loss Function**: CrossEntropyLoss
- **Optimizer**: Adam (`lr=0.0001`)
- **Epochs**: 10
- **Framework**: PyTorch

---

## 📊 Training Results

The model achieved high classification performance during training with increasing confidence in detecting aggressive ROP. A confidence-based trust metric is used instead of raw accuracy.

---

## ⚡ Real-Time Inference

Run the model interactively with:

```bash
python predict_real_time.py
🔍 Prediction: AROP1  
🔐 Confidence: 0.9412  
📊 Trust Score: ✅ High Trust  
🧠 Diagnosis: ✅ Retinopathy Detected  
