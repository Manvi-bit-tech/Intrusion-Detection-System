# AI-Driven Adaptive Intrusion Detection and Network Threat Intelligence Framework using Transformer-Based Temporal Anomaly Detection

## Overview

Cybersecurity systems face increasingly sophisticated attacks that exhibit complex temporal and behavioral patterns. Traditional signature-based Intrusion Detection Systems (IDS) often fail to detect previously unseen attacks, while many machine learning approaches lack interpretability, making them difficult to trust in operational environments.

This project proposes an **AI-driven adaptive Intrusion Detection and Network Threat Intelligence Framework** that combines **Transformer-based temporal anomaly detection**, **Hybrid Temporal Representation Engineering (HTRE)**, **SHAP Explainable Artificial Intelligence (XAI)**, and an automated **Threat Intelligence Engine**.

The framework not only detects multiple categories of network attacks but also explains why a prediction was made and enriches the prediction with contextual threat intelligence including severity assessment, MITRE ATT&CK mapping, risk prioritization, and actionable security recommendations.

---

# Framework Overview

```
                         CICIDS2018 Dataset
                                 │
                                 ▼
                      Data Preprocessing
                                 │
                                 ▼
                 Hybrid Temporal Representation
                     Engineering (HTRE)
                                 │
                                 ▼
          Transformer-Based Temporal Anomaly Detection
                                 │
                                 ▼
                     Multi-Class Attack Prediction
                                 │
                                 ▼
                    SHAP Explainability Engine
                                 │
                                 ▼
                  Threat Intelligence Framework
                                 │
                                 ▼
                Comprehensive Threat Assessment Report
```

---

# Project Objectives

The primary objectives of this framework are:

- Detect multiple categories of network attacks using a Transformer-based architecture.
- Improve detection capability through temporal feature engineering.
- Provide transparent and interpretable predictions using SHAP.
- Convert raw IDS predictions into actionable cyber threat intelligence.
- Support security analysts with automated risk assessment and response recommendations.

---

# Dataset

The framework is developed using the **CICIDS2018** dataset.

### Dataset Characteristics

- Realistic network traffic
- Modern attack scenarios
- Benign and malicious traffic
- Flow-based network features
- Multiple attack categories

### Attack Classes

- Benign
- DDoS
- DoS Hulk
- DoS GoldenEye
- DoS Slowloris
- DoS SlowHTTPTest
- Bot
- FTP-Patator
- SSH-Patator
- PortScan
- Web Attack – Brute Force
- Web Attack – XSS
- Web Attack – SQL Injection
- Heartbleed
- Infiltration

> **Note:** The dataset is not included in this repository due to licensing and repository size limitations.

---

# Proposed Methodology

The proposed framework consists of four major stages.

## Stage 1 — Data Preprocessing

The CICIDS2018 dataset undergoes preprocessing to prepare high-quality inputs for deep learning.

The preprocessing pipeline includes:

- Missing value handling
- Infinite value removal
- Feature normalization
- Label encoding
- Dataset balancing (where applicable)
- Train-test splitting

---

## Stage 2 — Hybrid Temporal Representation Engineering (HTRE)

Instead of relying only on the original CICIDS2018 flow features, the framework introduces additional temporal representations to better capture network behavior.

### Original Network Features

The Transformer model utilizes the original flow-level features provided by CICIDS2018, including:

- Flow Duration
- Total Forward Packets
- Total Backward Packets
- Flow Bytes/s
- Flow Packets/s
- Packet Length Statistics
- Inter Arrival Time (IAT) Features
- TCP Flag Features
- Window Size Features
- Active and Idle Time Features
  ... and 69 others

These features describe statistical characteristics of network flows.

### Proposed HTRE Features

To improve temporal anomaly detection, several engineered temporal features are introduced.

| Feature | Purpose |
|----------|---------|
| TRE_LogFlowBytes | Logarithmic representation of flow bytes to reduce scale variation |
| TRE_LogFlowBytsChange | Captures temporal variation in transmitted bytes |
| TRE_FlowRate | Represents normalized traffic flow rate |
| TRE_PacketRate | Models packet transmission dynamics |
| TRE_BurstScore | Captures bursty traffic behaviour |
| TRE_IATVariation | Measures temporal variation in packet inter-arrival time |

These engineered features enable the Transformer to learn temporal relationships more effectively than using raw flow statistics alone.

---

# Stage 3 — Transformer-Based Temporal Anomaly Detection

The core IDS is based on a Transformer architecture adapted for network intrusion detection.

## Detection Pipeline

```
Input Features
      │
      ▼
Feature Normalization
      │
      ▼
HTRE Feature Integration
      │
      ▼
Feature Embedding
      │
      ▼
Positional Encoding
      │
      ▼
Multi-Head Self Attention
      │
      ▼
Feed Forward Network
      │
      ▼
Dropout & Layer Normalization
      │
      ▼
Dense Classification Layer
      │
      ▼
Softmax Output
      │
      ▼
Attack Prediction
```

### Transformer Components

The model includes:

- Input embedding
- Positional encoding
- Multi-head self-attention
- Feed-forward neural network
- Layer normalization
- Dropout regularization
- Dense classification layer
- Softmax output layer

The self-attention mechanism enables the model to capture long-range dependencies and temporal relationships within network traffic.

---

# Stage 4 — Explainable AI using SHAP

Deep learning models often operate as black boxes.

To improve interpretability, SHAP (SHapley Additive exPlanations) is integrated into the framework.

The explainability module provides:

- Global feature importance
- Class-wise feature importance
- Local prediction explanations
- Top influential features for each detected attack

Generated outputs include:

- SHAP summary plots
- Feature importance CSV files
- Class-wise importance rankings
- Local feature contribution analysis

This enables analysts to understand why a particular attack prediction was produced.

---

# Threat Intelligence Framework

Rather than stopping at attack classification, the framework transforms IDS predictions into actionable cyber threat intelligence.

## Threat Intelligence Pipeline

```
Predicted Attack
        │
        ▼
Knowledge Base Lookup
        │
        ▼
Severity Assessment
        │
        ▼
Risk Score Calculation
        │
        ▼
Risk Classification
        │
        ▼
Priority Assignment
        │
        ▼
MITRE ATT&CK Mapping
        │
        ▼
Security Recommendations
        │
        ▼
Threat Assessment Report
```

The generated report includes:

- Predicted attack
- Confidence score
- Attack category
- Attack description
- Top influential SHAP features
- Threat severity
- Risk score
- Risk level
- Priority level
- MITRE ATT&CK mapping
- Recommended mitigation actions

---

# Example Threat Report

```
Prediction        : SQL Injection

Confidence (%)    : 96.8

Category          : Web Application Attack

Description       : An attack that injects malicious SQL statements into application inputs to manipulate backend databases.

Top Influential Features

• Fwd Pkt Len Mean
• Fwd Seg Size Min
• TRE_LogFlowBytsChange
• Init Bwd Win Byts
• Fwd Pkt Len Max

Severity          : Critical

Risk Score        : 96.8

Risk Level        : Critical

Priority          : P1

MITRE ATT&CK      : T1190 - Exploit Public-Facing Application (Initial Access)

Recommendations

1. Inspect web server logs.
2. Validate application input filtering.
3. Apply security patches.
4. Deploy or update Web Application Firewall (WAF) rules.
```

---

# Key Contributions

The proposed framework introduces several contributions:

- Transformer-based temporal intrusion detection
- Hybrid Temporal Representation Engineering (HTRE)
- Enhanced temporal feature representation
- SHAP-based explainable AI for IDS
- Class-wise feature attribution
- Automated Threat Intelligence generation
- MITRE ATT&CK integration
- Risk-based attack prioritization
- Automated security recommendations
- Human-readable threat assessment reports

---

# Technologies Used

- Python
- TensorFlow / Keras
- NumPy
- Pandas
- Scikit-learn
- SHAP
- Matplotlib
- Seaborn

---

# Installation

```bash
git clone <repository_url>

cd <repository_name>

pip install -r requirements.txt
```

---

# License

This project is intended for academic research and educational purposes.

---

# Citation

If you use this work in your research, please cite the associated thesis or future publication.
