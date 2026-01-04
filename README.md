# Handwritten Digit Recognition using PCA and KNN

**Project Type:** Computer Vision • Dimensionality Reduction • Classical ML  
**Status:** Completed  
**Dataset:** MNIST  

---

## 📌 Overview
This project explores handwritten digit recognition using classical machine learning techniques instead of deep learning. The goal was to understand how dimensionality reduction affects model performance and computational efficiency.

Using the **MNIST dataset** (28×28 grayscale images), I evaluated how **Principal Component Analysis (PCA)** can compress high-dimensional image data while retaining most of the information required for accurate classification using **K-Nearest Neighbors (KNN)**.

---

## ❓ Problem Statement
Each MNIST image contains **784 pixel features**. High dimensionality increases:
* **Computational cost:** Training and prediction times grow exponentially.
* **Distance sparsity:** The "Curse of Dimensionality" makes distance-based metrics (like those in KNN) less effective.

**Question explored:** Can PCA reduce dimensionality significantly without sacrificing much accuracy?

---

## 🛠️ Tech Stack
* **Language:** Python
* **Libraries:** NumPy, Pandas, Matplotlib, Scikit-learn
* **Techniques:** * Data Standardization
    * Principal Component Analysis (PCA)
    * K-Nearest Neighbors (KNN) Classification

---

## ⚙️ Methodology

### 1. Data Exploration & Visualization
* MNIST images reshaped from flattened vectors into 28×28 grids.
* Visual inspection used to understand digit structure and variance.

### 2. Preprocessing
* **StandardScaler** applied to normalize pixel intensities.
* This is critical because KNN relies on distance-based calculations, making it sensitive to the scale of features.
* The standardization formula used:
    $$z = \frac{x - \mu}{\sigma}$$

### 3. Baseline Model (KNN without PCA)
* KNN trained on all 784 pixel features.
* Served as a performance benchmark for comparison.

### 4. Dimensionality Reduction (PCA)
* PCA applied to capture directions of maximum variance.
* Number of components chosen based on the **explained variance ratio**.
* Dataset reduced from **784 → 100 dimensions**.

---

## 📊 Results

| Model | Dimensions | Accuracy | Remarks |
| :--- | :--- | :--- | :--- |
| **KNN (Baseline)** | 784 | ~96.5% | High accuracy but computationally expensive |
| **PCA + KNN** | 100 | ~95.4% | Significantly faster with minimal loss in accuracy |

> **Key Insight:** Reducing dimensionality by **~87%** resulted in only a **~1.1% drop** in accuracy, demonstrating that most useful information lies in a much lower-dimensional subspace.

---

## 💡 Learnings & Takeaways
* **Efficiency:** High-dimensional pixel space is inefficient for distance-based models; PCA provides a necessary compression layer.
* **Structural Patterns:** PCA effectively captures the primary structural patterns in handwritten digits.
* **Fundamentals Matter:** Classical ML methods can perform competitively when paired with proper preprocessing and feature engineering.

---

## 👤 Author
**Harneet Kaur** *M.Sc. Data Science* 📌 **Focus areas:** Machine Learning • Statistics • Applied Data Science
