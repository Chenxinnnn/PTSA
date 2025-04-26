# 📊 Real-Time Ad Performance Anomaly Detection

This project aims to evaluate and compare various anomaly detection algorithms for identifying anomalies in real-time online advertisement performance metrics, specifically **cost-per-click (CPC)** and **cost-per-thousand-impressions (CPM)**. The work was conducted as part of the course [DS-GA 1018 Probabilistic Time Series Analysis](https://cds.nyu.edu/), NYU.

## 🧠 Research Question

> How can different anomaly detection algorithms effectively identify anomalies in real-time ad performance metrics (e.g., CPC and CPM), and which model provides the most accurate early detection?

---

## 📁 Repository Structure

```plaintext
PTSA/
├── ad_anomaly/
│   ├── NAB-master/                 # Cloned & modified NAB benchmark
│   │   ├── data/realAdExchange/   # Dataset used: CPC, CPM with anomaly labels
│   │   ├── results/               # Model outputs and NAB scores
│   │   ├── scripts/               # Utility and visualization scripts
│   │   └── README.md              # NAB’s original description
│   ├── PTSA_Final_Project.ipynb   # Final notebook comparing models
│   └── PTSA_Proposal.pdf          # Original project proposal
└── README.md                      # This file (project overview)
```

## 📂 Dataset

We use the **realAdExchange** dataset from the [Numenta Anomaly Benchmark (NAB)](https://github.com/numenta/NAB), which contains time series data of ad performance over time.  
- Each entry corresponds to a specific time interval (e.g., hourly)
- Contains known labeled anomalies (e.g., spikes or drops in CPM/CPC)

**Key Metrics**:
- **CPC (Cost-Per-Click)**: cost incurred per ad click  
- **CPM (Cost-Per-Thousand-Impressions)**: cost incurred per 1000 ad impressions

---

## 🧪 Methods

We implemented and compared both traditional statistical models and machine learning approaches:

### 📈 Statistical Models
- **ARMA** (AutoRegressive Moving Average)  
- **HMM** (Hidden Markov Models)  

### 🤖 Machine Learning Models
- **LSTM** (Long Short-Term Memory Networks)  
- **One-Class SVM** (Support Vector Machines for anomaly detection)

---

## 🧮 Evaluation Metric

We use the **NAB Score**, which:
- Rewards early and accurate anomaly detection
- Penalizes late detections and false positives
- Supports real-time applications with time-sensitive priorities

---

## ✅ Results (on CPM data)

| Model      | NAB Score | TP | FP | FN | TN |
|------------|-----------|----|----|----|----|
| ARMA       | **1.2747** | 3  | 3  | 161| 1476 |
| HMM (DHMM) | 0.4748    | 3  | 11 | 161| 1468 |
| LSTM       | -5.4300   | 0  | 13 | 164| 1466 |

> **Finding**: In this task, **statistical models (ARMA, HMM)** significantly outperformed the LSTM-based deep learning approach in both precision and NAB score.

---

## 📚 Reference

Lavin, A. & Ahmad, S. (2015). *Evaluating Real-Time Anomaly Detection Algorithms – The Numenta Anomaly Benchmark.* IEEE ICMLA. [Link](https://ieeexplore.ieee.org/document/7396687)

---

## 🛠️ Tools & Libraries

- Python, NumPy, Pandas, Scikit-learn  
- Statsmodels, hmmlearn, TensorFlow/Keras  
- Matplotlib, Seaborn

---

## 📌 Course Info

This project was completed as part of **DS-GA 1018: Probabilistic Time Series Analysis**  
Instructor: Prof. [Sebastian Wagner-Carena](https://cds.nyu.edu/)
