# 📊 Alloy 2024 Fraud Benchmark & Financial Risk Analytics

![Python Version](https://img.shields.io/badge/python-3.9%2B-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Domain](https://img.shields.io/badge/domain-Fraud%20Analytics%20%26%20Risk-red.svg)
![Data Source](https://img.shields.io/badge/data--source-Alloy%202024%20Report-brightgreen.svg)

An analytical Python codebase and visualization suite built around **Alloy's 2024 State of Fraud Benchmark Report**. This repository provides data structures, exploratory data analysis (EDA), and automated visualization tools for benchmarking fraud losses, attack vector frequencies, and technology investments across US and UK financial institutions, fintechs, and credit unions.

---

## 📋 Table of Contents

- [Executive Summary](#-executive-summary)
- [Key Benchmark Findings](#-key-benchmark-findings)
- [Visual Dashboard](#-visual-dashboard)
- [Installation](#-installation)
- [Quickstart Guide](#-quickstart-guide)
- [Dataset Architecture](#-dataset-architecture)
- [Project Structure](#-project-structure)
- [Contributing](#-contributing)
- [License](#-license)

---

## 📌 Executive Summary

Fraud vectors are evolving rapidly across consumer and commercial banking channels. Based on industry benchmark data from Alloy's 2024 report surveying decision-makers at financial institutions, this project analyzes:
1. **Direct Loss Distributions**: Financial impact tiers ranging from under $100k to over $10M.
2. **YoY Attack Frequencies**: Longitudinal trends across consumer vs. business accounts.
3. **Attack Vector Prevalence**: Relative ranking of Authorized Push Payment (APP) fraud, Bust-out fraud, Account Takeover (ATO), and Identity Theft.
4. **ROI & Prevention Spend**: Operational budget allocations relative to realized fraud losses.

---

## 📈 Key Benchmark Findings

- **High Loss Thresholds**: **57%** of financial institutions experienced direct fraud losses exceeding **$500,000** over the past 12 months, with **25%** incurring over **$1,000,000**.
- **Surging Attack Volumes**: **62%** of institutions reported an increase in fraud attempts targeting consumer accounts, while **52%** observed increases in business account attacks.
- **Top Fraud Vectors**:
  - **Authorized Push Payment (APP) Fraud** is the #1 vector in the UK (**29%** ranking as most frequent).
  - **Bust-out Fraud** leads in the US (**21%** ranking as most frequent), followed by APP fraud (**17%**).
- **Prevention Budgets**: **64%** of institutions spend over **$500,000** annually on anti-fraud technologies, identity decisioning tools, and recovery operations.

---

## 🎨 Visual Dashboard

The repository includes an automated script that produces a 4-quadrant executive visualization dashboard (`alloy_2024_fraud_analysis.png`):

```
+------------------------------------+------------------------------------+
| 1. Direct Fraud Loss Distribution   | 2. YoY Attack Frequency Trend      |
|    (US vs UK Comparison Bar Chart) |    (Consumer vs Business Accounts) |
+------------------------------------+------------------------------------+
| 3. Top Fraud Types by Case Volume  | 4. Loss vs. Prevention Spend       |
|    (Horizontal Vector Breakdown)   |    ($500k+ Threshold Benchmark)    |
+------------------------------------+------------------------------------+
```

---

## ⚙️ Installation

### Prerequisites
- Python 3.9+
- `pip` or `conda`

### Clone Repository & Install Dependencies

```bash
git clone https://github.com/your-username/alloy-2024-fraud-analytics.git
cd alloy-2024-fraud-analytics
```

Create a virtual environment:

```bash
# macOS/Linux
python3 -m venv venv
source venv/bin/activate

# Windows
python -m venv venv
venv\Scripts\activate
```

Install requirements:

```bash
pip install -r requirements.txt
```

#### `requirements.txt`
```text
numpy>=1.21.0
pandas>=1.3.0
matplotlib>=3.4.0
seaborn>=0.11.0
```

---

## 🚀 Quickstart Guide

Generate the analysis dataframes and the visual dashboard locally:

```bash
python generate_dashboard.py
```

### Python API Example

```python
import pandas as pd
from analytics import load_alloy_loss_data, plot_fraud_summary

# Load direct fraud loss distribution dataset
df_losses = load_alloy_loss_data()

# Filter institutions with >$500k direct loss
high_loss_us = df_losses[df_losses['Loss Bracket'].isin(['$500k - $1M', '$1M - $10M', 'Over $10M'])]['US (%)'].sum()
print(f"Percentage of US institutions losing >$500k: {high_loss_us}%")

# Generate executive plot
plot_fraud_summary(output_filename="alloy_2024_fraud_analysis.png")
```

---

## 📂 Dataset Architecture

The dataset is structured as tabular dictionaries covering four principal benchmarks:

```text
├── Direct Losses Tiers ($1-$100k, $100k-$500k, $500k-$1M, $1M-$10M, >$10M)
├── YoY Attack Frequency (Increased, Stayed Same, Decreased)
├── Fraud Vectors (APP Fraud, Bust-out, ATO, Identity Theft, Check, ACH, Chargeback)
└── Budget Thresholds (Loss >$500k vs Prevention Spend >$500k)
```

---

## 📁 Project Structure

```text
alloy-2024-fraud-analytics/
├── README.md
├── requirements.txt
├── LICENSE
├── generate_dashboard.py         # Main script for data processing & chart generation
├── alloy_2024_fraud_analysis.png # Rendered executive dashboard artifact
└── src/
    ├── __init__.py
    ├── data_loader.py            # Alloy benchmark data definitions
    └── visualization.py         # Matplotlib multi-panel figure code
```

---

## 🤝 Contributing

Contributions are welcome! If you'd like to extend the dataset with additional industry reports or add predictive modeling modules:
1. Fork the repository.
2. Create your feature branch (`git checkout -b feature/Add2025Data`).
3. Commit your changes (`git commit -m 'Add 2025 projection models'`).
4. Push to the branch (`git push origin feature/Add2025Data`).
5. Open a Pull Request.

---

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.
