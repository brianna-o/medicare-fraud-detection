# Medicare Part D Fraud Detection
### Texas 2023 | Anomaly Detection & Provider Risk Scoring

## Project Overview
This project analyzes 1.8 million Medicare Part D prescription records from Texas to identify providers exhibiting statistically anomalous billing patterns consistent with fraud, waste, and abuse. Using CMS public data, this analysis surfaces 100 high-risk providers representing $274.5 million in suspicious Medicare spending.

## Key Findings
- 62,301 Texas providers analyzed across 1,449 unique drugs
- 100 providers flagged (0.16% flagging rate)
- $274.5M in potentially suspicious spend identified
- 6 Critical Risk providers with composite risk scores above 10
- 16 Ophthalmologists flagged for prescribing opioids (specialty mismatch)
- Nurse Practitioners and Physician Assistants disproportionately represented in top risk tier

## Methodology
1. Data Collection - CMS Medicare Part D Prescribers by Provider and Drug (2023), filtered to Texas
2. Feature Engineering - derived cost_per_claim, days_per_claim, and is_brand columns
3. Peer Group Benchmarking - Z-scores calculated per provider against specialty peer group
4. Risk Scoring - composite score weighted 40% cost, 30% days supply, 30% claims volume
5. Specialty Mismatch Detection - flagged providers prescribing outside specialty scope

## How to Reproduce
1. Clone this repository
2. Create virtual environment: python3 -m venv venv && source venv/bin/activate
3. Install dependencies: pip install -r requirements.txt
4. Download Medicare Part D Prescribers by Provider and Drug (2023) from https://data.cms.gov
5. Place CSV in data/raw/
6. Run notebooks in order: 01 through 05

## Technologies Used
- Python 3.12, Pandas, NumPy, Matplotlib, Seaborn, Folium, Scikit-learn, Jupyter

## Data Source
Centers for Medicare & Medicaid Services (CMS)
Medicare Part D Prescribers by Provider and Drug
https://data.cms.gov

## Author
Brianna | Data Analyst
https://github.com/brianna-o