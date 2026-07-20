# Dataset

This framework is developed using the **CSE-CIC-IDS2018** dataset, a comprehensive benchmark intrusion detection dataset jointly developed by the **Communications Security Establishment (CSE), Canada** and the **Canadian Institute for Cybersecurity (CIC), University of New Brunswick**. The dataset was designed to provide a realistic and reproducible evaluation environment for network intrusion detection systems by capturing modern enterprise network traffic under diverse benign and attack scenarios. :contentReference[oaicite:0]{index=0}

Unlike earlier static benchmark datasets, CSE-CIC-IDS2018 was generated using a **profile-based methodology**, where realistic user behaviors (B-Profiles) and attack scenarios (M-Profiles) were combined to simulate normal enterprise activities alongside coordinated cyber attacks. The experimental infrastructure consists of **420 client machines**, **30 servers**, **five organizational departments**, and an attacking infrastructure of **50 machines**, closely resembling a real-world enterprise network. :contentReference[oaicite:1]{index=1}

Network traffic was captured over **10 days** and processed using **CICFlowMeter-V3**, which extracts more than **80 bidirectional statistical flow features** describing packet statistics, flow duration, inter-arrival times, TCP flags, packet lengths, window sizes, active/idle times, and other traffic characteristics. These flow features serve as the input to the proposed Transformer-based intrusion detection framework. :contentReference[oaicite:2]{index=2}

## Dataset Characteristics

| Property | Description |
|----------|-------------|
| Dataset | CSE-CIC-IDS2018 |
| Source | Communications Security Establishment (CSE) & Canadian Institute for Cybersecurity (CIC) |
| Collection Period | 10 Days |
| Environment | Enterprise Network Testbed |
| Traffic Type | Bidirectional Network Flow Records |
| Feature Extractor | CICFlowMeter-V3 |
| Original Features | 80+ Statistical Network Flow Features |
| File Format | CSV |

## Attack Categories - TOTAL : 14 classes

The dataset contains both benign traffic and multiple contemporary cyber attack scenarios, including:

- Benign
- FTP Brute Force
- SSH Brute Force
- DoS (Hulk, GoldenEye, Slowloris, SlowHTTPTest)
- DDoS (LOIC & HOIC)
- Botnet
- SQL Injection
- Cross-Site Scripting (XSS)
- Web Brute Force
- Infiltration

## Dataset Used in This Project

For this work, the **merged CSE-CIC-IDS2018 dataset** was used, where the traffic collected across all **10 capture days** is consolidated into a single CSV dataset. This merged version simplifies preprocessing and enables unified model training and evaluation while preserving the diversity of attack scenarios present throughout the complete collection period.

## Dataset Download

The merged dataset used in this project can be obtained from the Kaggle Data Card:

**Kaggle Data Card:**  
<https://www.kaggle.com/datasets/manvidhamija/cicidsmerged/data>

> **Note:** The dataset is not included in this repository due to its large size. Please download the merged dataset from the Kaggle page above before running the notebooks.

## Reference

Sharafaldin, I., Lashkari, A. H., & Ghorbani, A. A. (2018). *Toward Generating a New Intrusion Detection Dataset and Intrusion Traffic Characterization*. Proceedings of the 4th International Conference on Information Systems Security and Privacy (ICISSP). :contentReference[oaicite:3]{index=3}
