# 🌿 Hyperspectral Deep Neural Network for Wetland Vegetation Classification  

This repository contains a Deep Neural Network (DNN) implementation using **PyTorch** for **wetland vegetation classification** from **hyperspectral data**.  
The project explores spectral band reflectance data across **13 vegetation classes** and achieves a **test accuracy of ~97%** after hyperparameter optimization.  

---

## 📌 Project Overview  
- **Data:** Hyperspectral reflectance measurements across 176 bands  
- **Classes:** 13 wetland vegetation types (e.g., Oak Hammock, Mud Flats, Salt Marsh, Water Body, etc.)  
- **Samples:** 5211 labeled spectra  
- **Task:** Multi-class classification using a fully connected neural network  
- **Result:** Best configuration achieved **97.12% accuracy** on the test set  

---

## ⚙️ Features  
✅ Data preprocessing & normalization (StandardScaler)  
✅ Visualization of spectra & class heatmaps  
✅ Fully connected neural network with configurable architecture  
✅ GPU acceleration with CUDA  
✅ Model evaluation: Accuracy, Recall, Precision, F1 Score  
✅ Hyperparameter search (activation functions, optimizers, hidden layers, batch sizes)  
✅ Model saving & reproducibility  

---

## 🗂 Dataset  
Each vegetation class contains multiple hyperspectral samples (176-band vectors). Example:  

- **Mud Flats** → 503 samples × 176 bands  
- **Water Body** → 927 samples × 176 bands  

Unlike RGB (3 bands), hyperspectral imaging captures **176 narrow spectral bands**, providing much richer information for classification.  

---

## 🧠 Model Architecture  
- **Input Layer:** 176 nodes (bands)  
- **Hidden Layers:** Configurable (2–3 layers, 96–160 neurons)  
- **Output Layer:** 13 classes  
- **Best Performing Setup:**  
  - Hidden layers: `[160, 80, 40]`  
  - Activation: `LeakyReLU`  
  - Optimizer: `AdamW`  
  - Batch size: `64`  
  - Epochs: `200`  
- **Accuracy:** 97.12%  

---

## 📊 Results  
- **Training Accuracy:** ~100%  
- **Test Accuracy:** ~96–97%  
- **Model Parameters:** ~22k trainable  
- **Saved Model:** `Acc96_22285params_400epochs.torch`  

Performance Metrics:  
- Class-wise **Recall**, **Precision**, and **F1 Score** calculated  
- Highest accuracy with AdamW + LeakyReLU + 3 hidden layers  

---

## 🔧 Installation  
Clone the repository and install dependencies:  
```bash
git clone https://github.com/<your-username>/Hyperspectral-DNN.git
cd Hyperspectral-DNN
pip install -r requirements.txt
