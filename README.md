# 👁️ Handwritten Digit Recognition: PCA & KNN

**Project Status:** ✅ Completed | **Type:** Computer Vision / Dimensionality Reduction

### 🌸 Executive Summary
This project serves as my entry into **Computer Vision**, exploring how machines "see" and classify handwritten digits (0-9) using the famous **MNIST dataset**.

Instead of blindly throwing a deep neural network at the problem, I wanted to understand the mathematical foundations. I investigated whether **Principal Component Analysis (PCA)** could reduce the complexity of the image data (from 784 pixels down to ~100 components) while maintaining high classification accuracy with **K-Nearest Neighbors (KNN)**.

### 🛠️ Tech Stack
* **Language:** Python 🐍
* **Libraries:** `pandas`, `numpy`, `matplotlib`, `scikit-learn`
* **Techniques:** Data Standardization, PCA, Classification

### 📊 Methodology & Workflow

**1. Data Visualization**
We started with 28x28 pixel grayscale images.
* **Input:** Raw pixel intensities (0-255).
* **Process:** Reshaped flat vectors back into images to visualize the handwriting.

**2. Preprocessing**
* **Standardization:** Used `StandardScaler` to normalize pixel values (mean=0, variance=1). This is crucial for KNN, which relies on distance calculations.

**3. The Baseline Model (KNN)**
* Running KNN on the full 784 pixels resulted in **~96.48% accuracy**, but the computation was computationally heavy.

**4. Dimensionality Reduction (PCA)**
* I applied **PCA** to find the "principal components"—the directions of maximum variance in the images.
* **Result:** We compressed the data from 784 dimensions down to just **100 components**.

### 📉 Key Results

| Model | Dimensions | Accuracy | Notes |
| :--- | :--- | :--- | :--- |
| **Baseline KNN** | 784 pixels | **96.48%** | Slower, uses all raw data. |
| **PCA + KNN** | 100 components | **95.44%** | Faster, retained 99% of accuracy! |

> **Insight:** The "Elbow Method" analysis showed that after ~100 components, adding more information yielded diminishing returns on accuracy.

### 🧠 What I Learned
* **High dimensionality is a curse:** Working with raw pixels is inefficient.
* **PCA is powerful:** We can throw away nearly 87% of the raw pixel data and still recognize digits with 95% accuracy because PCA keeps the "essence" (structure) of the digit.
* **Computer Vision foundations:** Even without Convolutional Neural Networks (CNNs), simple geometric patterns in pixel data are enough for machines to distinguish numbers.

---
*Author: Harneet Kaur| MSc Data Science Student*
