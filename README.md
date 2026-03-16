# Insider Trading Detection

A machine learning system for detecting insider trading patterns in financial markets by analyzing trading data gathered from multiple sources.

## Overview

Insider trading — the buying or selling of securities based on material, non-public information — is difficult to detect through manual analysis alone due to the volume and complexity of market data. This project automates the detection process by applying machine learning models to identify statistically anomalous trading behavior that may indicate illicit activity.

## Goals

- Aggregate trading data from multiple financial data sources
- Engineer features that capture suspicious trading patterns (unusual volume spikes, timing relative to corporate events, etc.)
- Train and evaluate ML models to classify trades as normal or potentially suspicious
- Provide interpretable outputs to support human review and investigation

## How It Works

```
Data Sources → Ingestion & Normalization → Feature Engineering → ML Model → Anomaly Scores → Alerts
```

1. **Data Collection** — pull trading records from multiple sources (e.g., SEC EDGAR, market data APIs, corporate event filings)
2. **Preprocessing** — clean, normalize, and align data across sources and timeframes
3. **Feature Engineering** — extract signals such as:
   - Abnormal volume relative to historical baseline
   - Trade timing relative to earnings announcements, M&A filings, FDA approvals, etc.
   - Network relationships between traders and corporate insiders
   - Options activity patterns ahead of material events
4. **Modeling** — apply anomaly detection and/or supervised classification (e.g., Isolation Forest, XGBoost, neural networks)
5. **Scoring & Reporting** — rank suspicious activity and surface cases for review

## Data Sources

| Source | Data Type |
|--------|-----------|
| SEC EDGAR | Form 4 insider filings, 8-K/10-K disclosures |
| Market data APIs | Price, volume, options activity |
| Corporate event calendars | Earnings dates, M&A announcements |
| *(additional sources TBD)* | |

## Tech Stack

- **Language:** Python 3.x
- **ML:** scikit-learn, XGBoost, PyTorch *(planned)*
- **Data:** pandas, NumPy
- **Visualization:** matplotlib, seaborn *(planned)*
- **Data sources:** SEC EDGAR API, financial market data APIs

## Project Structure

```
Insider-Trading/
├── Insider_Trading/
│   ├── main.py          # Entry point
│   └── ...
├── data/                # Raw and processed datasets (gitignored)
├── notebooks/           # Exploratory analysis
├── models/              # Trained model artifacts
└── README.md
```

## Getting Started

### Prerequisites

```bash
python >= 3.9
```

### Installation

```bash
git clone https://github.com/300n/Insider_Trading.git
cd Insider_Trading
pip install -r requirements.txt
```

### Running

```bash
python main.py
```

## Disclaimer

This project is for **research and educational purposes only**. It is not intended to be used as legal evidence or as the sole basis for regulatory action. Detection outputs should always be reviewed by qualified professionals.
