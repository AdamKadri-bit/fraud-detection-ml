# Fraud Detection in Online Transactions

## Project Overview
Online transaction fraud results in significant financial losses and operational overhead for businesses. This project focuses on developing a machine learning–based fraud detection system that identifies potentially fraudulent online transactions while accounting for the highly imbalanced nature of fraud data.

The project emphasizes strong machine learning fundamentals, correct evaluation practices, and real-world decision reasoning rather than maximizing raw model accuracy.

---

## Problem Statement
This project aims to develop a machine learning model that supports automated fraud prevention by identifying high-risk online transactions. The model is designed to automatically block transactions with a high likelihood of fraud while flagging borderline cases for manual review. The primary consumer of the model’s output is an automated fraud prevention system, with secondary use by fraud analysts who review flagged transactions. In this context, false negatives are considered more costly because undetected fraudulent transactions lead to direct financial loss, whereas false positives mainly result in temporary transaction delays and increased operational workload.

---

## Decision Supported
- Automatically block transactions with a high predicted fraud risk
- Flag borderline transactions for manual review by fraud analysts

---

## Evaluation Metrics
Due to extreme class imbalance in fraud detection problems, accuracy is not used as a primary metric.

The model is evaluated using:
- **Recall (fraud class)** – ability to detect fraudulent transactions
- **Precision (fraud class)** – reliability of fraud predictions
- **PR-AUC** – robust performance metric for imbalanced datasets
- **Confusion Matrix** – interpretable error analysis

---

## Assumptions and Limitations
- The system is permitted to automatically block high-risk transactions
- The dataset is anonymized and may not capture all real-world fraud signals
- Fraud labels may be noisy or delayed
- Cost asymmetry exists between false positives and false negatives

---

## Project Structure
fraud-detection-ml/
├── data/
│ ├── raw/
│ └── processed/
├── notebooks/
│ ├── 01_problem_framing.ipynb
│ ├── 02_eda.ipynb
│ ├── 03_feature_engineering.ipynb
│ └── 04_modeling.ipynb
├── src/
│ ├── data_utils.py
│ ├── feature_utils.py
│ ├── model_utils.py
│ └── evaluation_utils.py
├── reports/
│ └── figures/
├── requirements.txt
└── README.md