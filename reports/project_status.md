# MMARAS Project Status Tracker

**Project:** Metro Manila Road Traffic Crash Analysis (MMARAS)  
**Institution:** Bulacan State University  
**Courses:** Data Mining · Data Science Programming · Data Visualization & Storytelling  
**Timeline:** 6-Week Academic Project  
**Last Updated:** March 2026  
**Overall Progress:** ~35%

---

## 📊 Progress Overview

| Phase | Description | Status | Progress |
|-------|-------------|--------|----------|
| Phase 1 | Data Collection & Cleaning | ✅ COMPLETE | 100% |
| Phase 2 | Exploratory Data Analysis | 🔄 IN PROGRESS | 63% |
| Phase 3 | Data Gap Resolution | 🔄 IN PROGRESS | 0% |
| Phase 4 | Machine Learning Models | ⏳ PENDING | 0% |
| Phase 5 | GIS Mapping | ⏳ PENDING | 0% |
| Phase 6 | Dashboard & Final Report | ⏳ PENDING | 0% |

---

## Phase 1 — Data Collection & Cleaning ✅ COMPLETE

All 8 primary datasets have been collected and cleaned.

| # | Dataset | File | Status |
|---|---------|------|--------|
| 1 | Monthly Casualties | `Monthly_casualties.csv` | ✅ Complete |
| 2 | District/City Statistics | `District_City_Statistics_ML.csv` | ✅ Complete |
| 3 | AADT Traffic Volume | `AADT_ML.csv` | ✅ Complete |
| 4 | Accident Age Demographics | `Accident_age.csv` | ✅ Complete |
| 5 | Collision Type Statistics | `Collision_Type_Statistics_Raw.xlsx` | ✅ Complete |
| 6 | Vehicle Type Statistics | `Vehicle_Type_Statistics_Raw.xlsx` | ✅ Complete |
| 7 | Time of Day Statistics | `Time_of_Day_Statistics_Raw.xlsx` | ✅ Complete |
| 8 | Metro Manila Shapefiles | `gis/` directory | ✅ Complete |

---

## Phase 2 — Exploratory Data Analysis 🔄 IN PROGRESS (63%)

| # | Notebook | Topic | Status |
|---|----------|-------|--------|
| 01 | `01_EDA_Monthly_Casualties.ipynb` | Monthly crash trends 2015–2024 | ✅ Complete |
| 02 | `02_EDA_District_City_Casualties.ipynb` | City/district casualty breakdown | ✅ Complete |
| 03 | `03_EDA_Accident_District.ipynb` | District-level accident patterns | ✅ Complete |
| 04 | `04_EDA_Accident_Age_Demographics.ipynb` | Age bracket crash demographics | ✅ Complete |
| 05 | `05_EDA_AADT_Traffic_Volume.ipynb` | Traffic volume analysis | ✅ Complete |
| 06 | Collision Type EDA | Crash counts by collision type | ⏳ TODO |
| 07 | Vehicle Type EDA | Crash involvement by vehicle type | ⏳ TODO |
| 08 | Time of Day EDA | Crash distribution by time bracket | ⏳ TODO |

---

## Phase 3 — Data Gap Resolution 🔄 IN PROGRESS

See full research brief: [`reports/data_gap_research_brief.md`](data_gap_research_brief.md)

| Priority | Gap | Blocking Model | Status |
|----------|-----|---------------|--------|
| 🔴 CRITICAL | Gap 1: Causation / Contributing Factors | Logistic Regression | ⏳ Searching |
| 🟠 HIGH | Gap 2: Gender-Disaggregated Data | Logistic Regression | ⏳ Searching |
| 🟠 HIGH | Gap 3: Road-Segment Crash Frequency | Random Forest (Hotspot) | ⏳ Searching |
| 🟡 MEDIUM | Gap 4: Supplementary / Verification Sources | Cross-validation & GIS | ⏳ Searching |

---

## Phase 4 — Machine Learning Models ⏳ PENDING

| # | Notebook | Model | Status | Blocker |
|---|----------|-------|--------|---------|
| 06 | `06_ML_TimeSeries_Forecasting.ipynb` | Prophet / ARIMA time series | 🔄 Ready to start | None — data available |
| 07 | `07_ML_RandomForest_Hotspot.ipynb` | Random Forest hotspot classifier | ⏳ Blocked | Gap 3 (road-segment data) |
| 08 | `08_ML_LogisticRegression_Demographics.ipynb` | Logistic Regression demographic risk | ⏳ Blocked | Gap 1 (causation) & Gap 2 (gender) |

---

## Phase 5 — GIS Mapping ⏳ PENDING

| Task | Description | Status |
|------|-------------|--------|
| KDE Hotspot Maps | Kernel density estimation of crash clusters | ⏳ Pending |
| Choropleth Maps | City-level crash severity maps | ⏳ Pending |
| Corridor Analysis | Major road crash corridor risk (EDSA, C5, etc.) | ⏳ Pending |
| Temporal-Spatial Overlays | AM/PM peak crash pattern maps | ⏳ Pending |

---

## Phase 6 — Dashboard & Final Report ⏳ PENDING

| Task | Description | Status |
|------|-------------|--------|
| Interactive Dashboard | Plotly/Streamlit or Power BI dashboard | ⏳ Pending |
| EDA Report | Full exploratory analysis write-up | ⏳ Pending |
| ML Model Report | Model results, evaluation, and interpretation | ⏳ Pending |
| Final Academic Report | Complete project report for submission | ⏳ Pending |
| Presentation | Slide deck for project defense | ⏳ Pending |

---

## 🔗 Key Documents

- 📄 [Data Gap Research Brief](data_gap_research_brief.md) — Full gap descriptions, search instructions, and workarounds
- 📓 Notebooks: `notebooks/` directory
- 🗺️ GIS Files: `gis/` directory
- 📁 Data: `data/` directory

---

*Update this file whenever a phase is completed or a data gap is resolved.*
