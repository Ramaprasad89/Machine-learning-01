# 💳 Credit Card Fraud Detection with Isolation Forest

This project demonstrates how to use **Isolation Forest**, an unsupervised machine learning algorithm, to detect credit card fraud. The tutorial covers data preprocessing, model training, and evaluation using key performance metrics such as **ROC AUC**, **confusion matrix**, and **classification report**. The project also includes advanced visualizations like anomaly score distributions, 3D scatter plots, and correlation heatmaps to interpret the model's behavior effectively.

---

## 🎯 **Objective**
The goal of this project is to develop a robust credit card fraud detection model using **Isolation Forest**. Unlike supervised learning models, Isolation Forest identifies outliers (potential fraud) without needing explicit labels during training. This makes it particularly suitable for fraud detection scenarios where fraud cases are rare and imbalanced.

---

## 📂 **Dataset Overview**
**Dataset:** Credit Card Fraud Detection Dataset  
- **Samples:** 284,807 (284,315 legitimate, 492 fraudulent)  
- **Features:** 31 total features  
  - **Time** – Time since first transaction in seconds  
  - **V1–V28** – PCA-transformed numeric features  
  - **Amount** – Transaction amount  
  - **Class** – Target variable (0 = legitimate, 1 = fraud)  

### **Target Distribution**  
| Class | Count | Proportion |
|-------|-------|------------|
| 0 (Legitimate) | 284,315 | 99.83% |
| 1 (Fraudulent) | 492 | 0.17% |

---

## 🏗️ **Model: Isolation Forest**
**Isolation Forest** is an anomaly detection algorithm that isolates data points by randomly selecting a feature and then randomly selecting a split value. Fraudulent transactions, being anomalies, are easier to isolate than legitimate ones.

### **Why Isolation Forest?**
✅ Works well with highly imbalanced datasets  
✅ No need for labeled data during training  
✅ Fast training and scoring, suitable for large datasets  
✅ Captures complex non-linear relationships  

### **Model Parameters**
| Parameter | Value | Description |
|-----------|-------|-------------|
| `contamination` | 0.01 | Estimated proportion of outliers |
| `random_state` | 42 | Reproducibility of results |

---

## 🚀 **Performance Metrics**
The model was evaluated using key classification metrics:

| Metric | Value |
|--------|-------|
| **Accuracy** | 0.99 (99%) |
| **Precision (Class 1 - Fraud)** | 0.11 |
| **Recall (Class 1 - Fraud)** | 0.66 |
| **F1-Score (Class 1 - Fraud)** | 0.18 |
| **ROC AUC Score** | 0.954 |

✅ **High ROC AUC** → Strong ability to distinguish between fraudulent and legitimate transactions.  

---

## 📊 **Results and Visualizations**
### 1. **Confusion Matrix**
Illustrates the number of correct and incorrect predictions:

| Actual / Predicted | Legitimate (0) | Fraud (1) |
|--------------------|----------------|-----------|
| **Legitimate (0)** | 56,311 | 553 |
| **Fraud (1)** | 33 | 65 |

- **True Positives:** 65  
- **False Positives:** 553  
- **False Negatives:** 33  
- **True Negatives:** 56,311  

---

### 2. **ROC Curve**
- **ROC AUC Score:** 0.954  
- The curve shows a high true positive rate at low false positive rates, indicating strong model discrimination.  
---

### 3. **Anomaly Score Distribution**
- Shows the distribution of anomaly scores.  
- Higher scores are assigned to normal transactions; lower scores to anomalies (fraud).  
---

### 4. **3D Scatter Plot**
- A 3D plot of `V1`, `V2`, and `Amount_scaled` shows distinct clusters for legitimate and fraudulent transactions.  
- Fraud cases tend to form outliers.  
---

### 5. **Correlation Heatmap**
- Highlights the correlation structure among PCA components (`V1–V28`) and transaction features (`Time`, `Amount`).  
- Most features have low correlations, consistent with PCA's dimensionality reduction effect.  
---

## ⚙️ **How to Run the Code**
### 1. **Clone the Repository**
```bash
git clone https://github.com/Ramaprasad89/credit-card-fraud-detection.git
cd credit-card-fraud-detection
