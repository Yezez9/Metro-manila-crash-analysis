# Metro-manila-crash-analysis
Machine learning + GIS analysis of 88,000+ Metro Manila road traffic crashes (MMARAS 2015–2024)

# 🚦 Metro Manila Road Traffic Crash Analysis (2015–2024)

> **An end-to-end data science project** analyzing ~88,000 annual crash records from the Metro Manila Accident Reporting and Analysis System (MMARAS), integrating machine learning, data mining, and GIS spatial analysis.

[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org)
[![Status](https://img.shields.io/badge/Status-In%20Progress-orange?style=flat-square)]()
[![Data](https://img.shields.io/badge/Records-88%2C101%20crashes-red?style=flat-square)]()
[![Coverage](https://img.shields.io/badge/Coverage-2015--2024-blue?style=flat-square)]()
[![Metro Manila](https://img.shields.io/badge/Region-Metro%20Manila%2C%20PH-FFD700?style=flat-square)]()

---

## 📌 Project Overview

Road traffic crashes remain a leading cause of preventable death in Metro Manila. This project applies data science and machine learning to **10 years of MMARAS crash data** to uncover patterns, predict future trends, and identify high-risk corridors across 17 cities.

**Key questions we answer:**
- Where and when do fatal crashes cluster in Metro Manila?
- Can we predict monthly crash volumes using time series models?
- Which demographic groups face the highest injury risk?
- What spatial patterns define crash hotspots?

---

## 📊 Dataset at a Glance

| Metric | Value |
|---|---|
| **Total Crashes (2024)** | 88,101 |
| **Fatal Crashes** | 427 |
| **Non-Fatal Injuries** | 21,910 |
| **Property Damage Only** | 65,764 |
| **Cities Covered** | 17 (all Metro Manila) |
| **Highest Crash City** | Quezon City (34,716 cases) |
| **Top Collision Type** | Side Swipe (26,313 cases) |
| **Motorcycles Involved** | 33,639 cases / 349 deaths |
| **Human Error Rate (Fatal)** | ~99% |

**Data source:** MMARAS Annual Reports, MMDA AADT Traffic Volume Data

---

## 🗂️ Repository Structure (In Progress)

```
metro-manila-crash-analysis/
│
├── 📁 data/
│   ├── raw/                    # Original MMARAS CSV/XLSX extracts
│   │   ├── Age_Classification_Statistics_Raw.xlsx
│   │   ├── AADT 2015-2024.csv
│   │   ├── Collision_Type_Statistics_Raw.xlsx
│   │   ├── District_City_Statistics_Raw.xlsx
│   │   ├── Fatalities_By_Person_Type_Raw.xlsx
│   │   ├── Injuries_By_Person_Type_Raw.csv
│   │   ├── Monthly_Statistics_Raw 2015-2024.csv
│   │   ├── Vehicle_Type_Statistics_Raw.xlsx
│   │   └── Time_of_Day_Statistics_Raw.xlsx
│   └── processed/              # Cleaned, transformed datasets
│
│
├── 📁 notebooks/
│   ├── 01_EDA_Monthly_Casualties.ipynb
│   ├── 02_EDA_District_City_Analysis.ipynb
│   ├── 03_EDA_Demographics_Age.ipynb
│   ├── 04_ML_TimeSeries_Forecasting.ipynb   # Prophet / ARIMA
│   ├── 05_ML_RandomForest_Hotspot.ipynb     # Hotspot Risk Classifier
│   └── 06_ML_LogisticRegression_Demo.ipynb  # Demographic Risk Profiling
│
├── 📁 gis/
│   ├── hotspot_maps/           # Kernel density, cluster maps
│   └── corridor_analysis/      # Major road crash corridors
│
├── 📁 reports/
│   ├── EDA_Report.pdf
│   └── figures/
│
├── 📁 dashboard/
│   └── (Interactive Plotly / Streamlit dashboard / Power BI)
│
├── requirements.txt
└── README.md
```

---

## 🤖 Machine Learning Models

### 1. Time Series Forecasting — `Prophet / ARIMA`
**Goal:** Predict monthly crash counts 6–12 months ahead  
**Input:** 10 years of monthly casualty data (120 data points)  
**Output:** Forecasted crash volume with confidence intervals  
**Status:** 🔄 In Progress

### 2. Random Forest Classifier — Hotspot Risk Prediction
**Goal:** Classify district-level crash risk (Low / Medium / High)  
**Features:** District, time of day, vehicle type, AADT traffic volume, collision type  
**Output:** Risk label per district per time window  
**Status:** 🔄 In Progress

### 3. Logistic Regression — Demographic Risk Profiling
**Goal:** Predict injury severity likelihood by age group  
**Features:** Age bracket, vehicle type, crash type, time  
**Output:** Probability of non-fatal injury vs. fatal outcome  
**Status:** 🔄 In Progress

---

## 📈 Key Findings (EDA — Preliminary)

> ⚠️ *Full findings pending. These reflect initial exploratory analysis.*

- **Motorcycles** are the deadliest vehicle type — involved in **38.2%** of all cases and **81.7%** of fatalities
- **Quezon City** alone accounts for **39.4%** of Metro Manila's total crashes

---

## 🗺️ GIS & Spatial Analysis

Using **QGIS** and **GeoPandas** for:
- Kernel Density Estimation (KDE) hotspot mapping
- District-level choropleth maps (crash severity by city)
- Major road corridor risk analysis (EDSA, C5, Commonwealth Ave.)
- Temporal-spatial overlays (AM/PM peak patterns)

---

## 🛠️ Tech Stack

| Category | Tools |
|---|---|
| **Language** | Python 3.10+ |
| **Data Processing** | Pandas, NumPy |
| **Visualization** | Matplotlib, Seaborn, Plotly |
| **Machine Learning** | Scikit-learn, Prophet, Statsmodels |
| **GIS** | GeoPandas, QGIS, Folium |
| **Notebooks** | Jupyter Lab |
| **Version Control** | Git / GitHub |

---

**Institution:** Bulacan State University  
**Courses:** Data Mining · Data Science Programming · Data Visualization & Storytelling  
**Timeline:** 6-Week Academic Project (2025)

---

## 🚀 Getting Started

```bash
# Clone the repo
git clone https://github.com/YOUR_USERNAME/metro-manila-crash-analysis.git
cd metro-manila-crash-analysis

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter
jupyter lab
```

### `requirements.txt`
```
pandas>=2.0.0
numpy>=1.24.0
matplotlib>=3.7.0
seaborn>=0.12.0
plotly>=5.15.0
scikit-learn>=1.3.0
prophet>=1.1.4
statsmodels>=0.14.0
geopandas>=0.13.0
folium>=0.14.0
openpyxl>=3.1.0
jupyter>=1.0.0
```

---

## 📋 Data Gap Research

This project has identified **4 critical data gaps** that need to be resolved before ML models can be fully trained. See the full research brief:

📄 **[Data Gap Research Brief](reports/data_gap_research_brief.md)** — Detailed gap descriptions, search instructions, and workarounds  
📊 **[Project Status Tracker](reports/project_status.md)** — Current progress across all phases

| Priority | Gap | Status |
|----------|-----|--------|
| 🔴 CRITICAL | Causation/Contributing Factors | Searching |
| 🟠 HIGH | Road-Segment Crash Frequency | Searching |
| 🟠 HIGH | Gender-Disaggregated Data | Searching |
| 🟡 MEDIUM | Supplementary/Verification | Searching |

---

## 📅 Project Roadmap (35% Progress)

- [x] Data collection & extraction from MMARAS Annual Reports (2015–2024)
- [x] Dataset assembly — 8 datasets collected and cleaned
- [x] Initial preprocessing & feature engineering
- [x] EDA — Monthly Casualties, District/City, Accident District, Age Demographics, AADT
- [ ] EDA — Collision Type, Vehicle Type, Time of Day
- [ ] Data gap resolution (Causation, Gender, Road-Segment data)
- [ ] Time Series Forecasting model (Prophet / ARIMA)
- [ ] Random Forest Hotspot Classifier
- [ ] Logistic Regression Demographic Model
- [ ] GIS hotspot maps
- [ ] Interactive dashboard
- [ ] Final report & presentation

---

## ⚠️ Data Notes

- Data sourced from **official MMARAS Annual Reports** (MMDA)
- Aggregate-level data (not individual incident records) used for ML modeling
- AADT data represents annual average daily traffic counts per road segment
- Some years may have minor reporting inconsistencies across districts

---

## 📄 License

This project is for **academic research purposes only**. Data is sourced from publicly available MMDA/MMARAS annual reports.

---

<p align="center">
  <i>Built to help make Metro Manila's roads safer — one data point at a time.</i>
</p>
