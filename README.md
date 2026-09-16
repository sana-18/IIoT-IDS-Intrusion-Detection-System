# CIC IoT - Multi-Class Intrusion Detection for Industrial IoT Networks

## Project Overview

This repository presents a **multi-class Intrusion Detection System (IDS)** for **Industrial Internet of Things (IIoT)** networks.
The project focuses on detecting and classifying **multiple IoT attack types** using a rigorous **machine learning and deep learning pipeline**, combining advanced preprocessing, exploratory data analysis (EDA), feature selection, and a comparative study of classical ML, gradient boosting, and neural network models.
This project was completed as part of the Big Data Analytics module at the National Institute of Posts & Telecommunications (INPT), Rabat.

The work is based on an academic research study and a complete experimental notebook, designed to be **reproducible**, **scalable**, and **industry-oriented**.

---

## Objectives

* Build a **multi-class IDS** for IIoT traffic (not binary detection)
* Handle **severe class imbalance** typical of real IoT networks
* Perform **advanced preprocessing and feature engineering**
* Compare:

  * Classical ML models
  * Gradient Boosting models
  * Deep Learning models (MLP, MLP with Attention)
  * Transformer-based tabular models
* Provide **clear performance benchmarks** and deployment insights

---

## Dataset Description

* **Total samples:** 685,671 network flows
* **Classes:** 8 (7 attacks + benign)
* **Attack types:**

  * Benign
  * Reconnaissance
  * DoS
  * DDoS
  * Man-in-the-Middle (MITM)
  * Malware
  * Web Attacks
  * Brute Force
* **Original features:** 94 network traffic features
* **Characteristics:**

  * Highly imbalanced (up to **66.6:1** ratio)
  * No missing values
  * Time-window–based aggregated network statistics

---

## Methodology

### 1. Data Preprocessing

* Merging multiple benign and attack CSV files
* Removal of metadata (timestamps, identifiers) to prevent data leakage
* Encoding categorical features using **Ordinal Encoding**
* Standardization of numerical features using **StandardScaler**

### 2. Feature Selection

* **Permutation Importance** using a Random Forest model
* Selection of **top 70 most informative features**
* Focus on packet size, timing, port, and protocol statistics

### 3. Class Imbalance Handling

* **Inverse frequency class weighting**
* Stratified train/test split (80/20)
* Macro-averaged evaluation metrics

---

## Models Implemented

### Classical Machine Learning

* Decision Tree (DT)
* Random Forest (RF)
* Extra Trees (ET)

### Gradient Boosting

* XGBoost (XGB)
* LightGBM (LGBM)
* CatBoost (CAT)

### Deep Learning

* Multi-Layer Perceptron (MLP)
* MLP with Attention mechanism (MLP-A)

### Transformer-Based Tabular Models

* TabFormer (TF)
* NODE-like model with Attention (NODE-A)

All models use **identical preprocessing and feature sets** to ensure fair comparison.

---

## Results Summary

| Model           | Accuracy   | Macro F1   | Training Time |
| --------------- | ---------- | ---------- | ------------- |
| Random Forest   | **97.21%** | **0.9660** | 43s           |
| Extra Trees     | 97.14%     | 0.9649     | 41s           |
| Decision Tree   | 97.00%     | 0.9618     | 12s           |
| XGBoost         | 96.52%     | 0.9616     | 87s           |
| MLP + Attention | 95.53%     | **0.9388** | 1859s         |
| TabFormer       | 92.89%     | 0.8762     | 1149s         |
| NODE-A          | 87.57%     | 0.7854     | 619s          |

**Key findings:**

* Random Forest achieves the **best overall performance**
* Deep learning models offer **marginal gains at high computational cost**
* Attention improves MLP performance but significantly increases training time
* Classical ensemble methods remain highly competitive for tabular IoT data

---

## Repository Structure

```bash
CIC-IoT-Intrusion-Detection/
│
├── notebook/
│   └── iot-analytics-project-final.ipynb
│
├── paper/
│   └── IoT_Analytics_Paper_Final.pdf
└── README.md
```

---

## Tech Stack

* **Language:** Python
* **Data Processing:** Pandas, NumPy
* **Machine Learning:** Scikit-learn
* **Gradient Boosting:** XGBoost, LightGBM, CatBoost
* **Deep Learning:** PyTorch / TensorFlow (MLP, Attention, Transformer)
* **Visualization:** Matplotlib, Seaborn

---

## Use Cases

* IIoT / Industrial Network Security
* Multi-class intrusion detection research
* Benchmarking ML vs Deep Learning on tabular data
* Feature importance analysis in network traffic
* Academic research and applied cybersecurity projects

---

## Author

**Sana Bakrim**
National Institute of Posts and Telecommunications (INPT)
Email: [business.sanabakrim@gmail.com](mailto:business.sanabakrim@gmail.com)

---

## Citation

If you use this work, please cite the associated paper:

```
Bakrim, S. (2024). 
A Multi-Class Intrusion Detection System for Industrial IoT Networks 
Using Machine Learning and Transformer-Based Tabular Approaches.
```

---

