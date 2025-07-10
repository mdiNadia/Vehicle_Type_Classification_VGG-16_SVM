# 🚗 Vehicle Type Classification using VGG-16 and SVM

**Project Type:** Reproduction and extension of a research paper
**Course:** Neural Networks and Deep Learning (NNDL) – MSc in Artificial Intelligence
**University:** University of Tehran
**Date:** February 2025

---

## 📄 Original Paper

**Title:** A Hybrid Deep Learning VGG-16 Based SVM Model for Vehicle Type Classification
**Journal:** Journal of Informatics and Web Engineering, Vol. 4 No. 1 (Feb 2025)
**Authors:** Muhammad Imran, Jafar Usman, Muhammad Muntazir Khan, Abdullah Khan
**eISSN:** 2821-370X

[Link to Paper (if available)](https://example.com)

---

## 📌 Project Description

This project reproduces and extends the key ideas proposed in the above research paper. The goal was to classify vehicle types using a hybrid model combining:

* **VGG-16** as a deep feature extractor
* **Support Vector Machine (SVM)** as the classifier

We compared this approach with multiple baselines, including VGG16 alone, AlexNet, and a simple custom CNN.

---

## 📦 Dataset

* **Source:** [Toyota Cars – 20K Labeled Images (Kaggle)](https://www.kaggle.com/datasets/occultainsights/toyota-cars-over-20k-labeled-images)
* **Selected Classes:** 10 randomly chosen Toyota vehicle models
* **Data Balancing:**

  * Each class adjusted to 500 samples
  * Augmentation used for low-sample classes: random rotation, flipping, brightness/contrast adjustment

---

## ⚙️ Implementation Details

### 🔹 Preprocessing

* Resized all images to 224x224 (RGB)
* Normalized pixel values to \[0, 1]
* Dataset split: 80% train / 20% test

### 🔹 Feature Extraction

* Used pre-trained **VGG-16** (Keras) without top layers
* Extracted feature vectors from final convolutional layers
* Flattened features saved and reused for SVM training
* Also tested **AlexNet** as alternative feature extractor

### 🔹 Classification Models

1. **VGG-16 only** (Softmax classifier)
2. **AlexNet only**
3. **Simple CNN** (3 conv layers)
4. **VGG-16 + SVM (Linear Kernel)**
5. **VGG-16 + SVM (RBF Kernel)**

### 🔹 Tools & Libraries

* Python, Keras, TensorFlow, Scikit-learn
* Google Colab, NumPy, Matplotlib

---

## 📊 Results Summary

| Model              | Accuracy   | Precision  | Recall     | F1 Score   |
| ------------------ | ---------- | ---------- | ---------- | ---------- |
| VGG-16             | 82.10%     | 0.8401     | 0.8210     | 0.8150     |
| AlexNet            | 80.60%     | 0.8083     | 0.8060     | 0.8038     |
| CNN (custom)       | 54.20%     | 0.4927     | 0.5420     | 0.5114     |
| VGG-16 + SVM       | 84.20%     | 0.8406     | 0.8420     | 0.8407     |
| VGG-16 + SVM (RBF) | **86.00%** | **0.8591** | **0.8600** | **0.8591** |

* VGG+SVM (RBF) showed the best performance overall.
* VGG alone also performed well, especially on high-frequency classes like *Camry* and *Tundra*.
* CNN model struggled due to limited depth and lower feature extraction capacity.

---

## 📈 Visualizations

* Confusion Matrices for all models
* Class distribution histogram
* Performance comparison plots (Accuracy, Precision, Recall, F1)

> 📁 See: `VGG_SVM12.ipynb`

---

## 📂 File Structure

```
├── VGG_SVM12.ipynb      # Main notebook (Google Colab)
├── report.pdf          # Full written report in Persian
├── README.md            # This file
└── dataset/             # (Not included, see Kaggle link)
```

---

## 💡 Key Takeaways

* Feature extraction using deep models significantly improves classical classifier performance
* Class balancing and data augmentation are critical in small/imbalanced datasets
* Combining pre-trained CNNs with SVMs provides a strong hybrid solution
* SVM with RBF kernel performs better than linear when class boundaries are nonlinear

---

## 📎 Reference

Imran, M., Usman, J., Khan, M. M., & Khan, A. (2025). *A Hybrid Deep Learning VGG-16 Based SVM Model for Vehicle Type Classification.* Journal of Informatics and Web Engineering, 4(1). eISSN: 2821-370X.

---

**📌 Note:** This project was completed as part of the "Neural Networks and Deep Learning" course under the supervision of Dr. E’rabi and Dr. Abolghasemi, University of Tehran.

> For questions or collaboration, feel free to contact me via GitHub or email.
