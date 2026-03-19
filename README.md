# CMS Heart Failure Readmission Analysis

Analyzing structural vs operational drivers of 30-day Heart Failure readmission 
penalties using CMS Hospital Compare FY2025 data. Built across 8 datasets 
covering 2,638 hospitals.

---

## Project Structure
```
CMS-HeartFailure-Readmission-Analysis/
│
├── data/
│   └── processed/
│       └── team7_master_dataset.csv   
│
├── notebooks/
│   └── BUS595_team7.ipynb            
│
└── README.md
```

---

## Data Sources

All raw data is from **CMS Hospital Compare FY2025**.  
Download the following files from:  
🔗 https://data.cms.gov/provider-data/topics/hospitals

| # | File | Description |
|---|------|-------------|
| 1 | `FY_2025_Hospital_Readmissions_Reduction_Program_Hospital.csv` | 30-day readmission rates — our target variable (ERR) |
| 2 | `Hospital_General_Information.csv` | Ownership, star rating, hospital type |
| 3 | `HCAHPS-Hospital.csv` | Patient experience survey scores |
| 4 | `Timely_and_Effective_Care-Hospital.csv` | Sepsis bundle, VTE, ED metrics |
| 5 | `FY_2025_HAC_Reduction_Program_Hospital.csv` | Patient safety scores (PSI-90) |
| 6 | `Medicare_Hospital_Spending_Per_Patient-Hospital.csv` | Medicare spending ratio |
| 7 | `Complications_and_Deaths-Hospital.csv` | Mortality and complication rates |
| 8 | `FY2021_Value_Based_Incentive_Payment_Amount.csv` | Value-based purchasing payments |

---

## How to Run

1. Download the 8 raw CSV files from the link above
2. Open `notebooks/BUS595_team7.ipynb` in Google Colab
3. Upload the files when prompted
4. Run all cells in order
5. Final merged dataset saves as `team7_master_dataset.csv`

---

## Team 7 — BUS 596 Master's Capstone
