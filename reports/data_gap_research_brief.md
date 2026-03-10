# MMARAS Data Gap Research Brief

**Project:** Metro Manila Road Accident Research and Analysis System (MMARAS)  
**Institution:** Bulacan State University  
**Date:** March 2026  
**Status:** Active Research Phase

---

## Section 1: Project Context

### Overview

The **MMARAS (Metro Manila Accident Recording and Analysis System)** project is a 6-week academic data science project at **Bulacan State University**, analyzing over 88,000 Metro Manila road traffic crashes recorded between **2015 and 2024**. The project integrates **data mining**, **machine learning (ML)**, and **GIS spatial analysis** to uncover crash patterns, identify high-risk corridors, and build predictive models.

**Primary Data Source:** MMARAS Annual Reports 2015–2024 (MMDA)

### Datasets Already Collected (All COMPLETE ✅)

| # | Dataset | Contents | Coverage |
|---|---------|----------|----------|
| 1 | `Monthly_casualties.csv` | Fatal, non-fatal, and property damage crashes per month | 2015–2024 |
| 2 | `District_City_Statistics_ML.csv` | Casualties by city/district across all 17 Metro Manila cities | 2015–2024 |
| 3 | `AADT_ML.csv` | Annual Average Daily Traffic volume by road and vehicle type | 2015–2024 |
| 4 | `Accident_age.csv` | Casualties broken down by age bracket | 2015–2024 |
| 5 | `Collision_Type_Statistics_Raw.xlsx` | Crash counts by collision type (side swipe, rear-end, head-on, etc.) | 2015–2024 |
| 6 | `Vehicle_Type_Statistics_Raw.xlsx` | Crash involvement by vehicle type (motorcycle, car, truck, jeep, etc.) | 2015–2024 |
| 7 | `Time_of_Day_Statistics_Raw.xlsx` | Crash distribution across time-of-day brackets | 2015–2024 |
| 8 | `Metro Manila Shapefiles` | City and barangay-level polygon geometries for GIS mapping | Current |

---

## Section 2: Machine Learning Models to Be Built

Three ML models are required deliverables for this project:

| Model | Method | Target Variable | Key Input Needed |
|-------|--------|----------------|-----------------|
| Time Series Forecasting | Prophet / ARIMA | Monthly crash count prediction | Historical monthly crash data **(HAVE ✅)** |
| Hotspot Risk Prediction | Random Forest Classifier | Classify road segment crash risk level | Road-level crash frequency + AADT **(PARTIALLY MISSING ⚠️)** |
| Demographic Risk Profiling | Logistic Regression | Predict fatal vs. non-fatal outcome | Age, gender, causation, time, vehicle type **(PARTIALLY MISSING ⚠️)** |

---

## Section 3: Critical Data Gaps — What to Find

### Gap 1 — Causation / Contributing Factors

> **Priority: 🔴 CRITICAL — Project cannot proceed without this**

#### What Is Missing

A table showing crash **causes or contributing factors** in Metro Manila by year. Categories include:
- Driver inattention / distraction
- Speeding / reckless driving
- Drunk driving / driving under influence
- Failure to yield
- Improper lane use / overtaking
- Mechanical failure / vehicle defect

#### Why It Matters

Causation is the **primary independent variable** for the Logistic Regression Demographic Risk model. Without causation data, the model cannot answer the core research question about which factors lead to fatal versus non-fatal outcomes. Project context already establishes that **human error causes ~99% of fatal crashes**, but this has not been extracted into a usable structured dataset.

#### Search Instructions

1. Search **MMARAS Annual Reports 2015–2024** for tables titled:
   - "Causation"
   - "Contributing Factors"
   - "Cause of Accidents"
   - "Human Error Breakdown"

2. Search **MMDA official website** ([mmda.gov.ph](http://mmda.gov.ph)) for downloadable road crash causation data or press releases.

3. Search **data.gov.ph** for crash causation datasets covering Metro Manila (keyword: "road crash cause", "accident cause", "contributing factors").

4. Search **academic papers and theses** using MMARAS data from:
   - DLSU (De La Salle University)
   - UP Diliman
   - Mapua University

5. If no downloadable dataset exists, **identify the exact page number and table number** in the MMARAS Annual Reports where causation data appears.

---

### Gap 2 — Gender-Disaggregated Crash Data

> **Priority: 🟠 HIGH — Required to strengthen Logistic Regression model**

#### What Is Missing

Casualty or crash involvement data **broken down by sex (male/female)** of the driver, passenger, or pedestrian. The existing `Accident_age.csv` contains age brackets but **no gender column**.

#### Why It Matters

The Logistic Regression model requires multiple demographic predictors to perform well. Using age alone produces a weak, potentially unreliable model. **Gender/sex is a standard variable** in global road safety datasets (WHO, OECD IRTAD, World Bank). Philippine crash report forms have historically omitted sex disaggregation, making this a known gap in local research.

#### Search Instructions

1. Search **MMARAS Annual Reports 2015–2024** for any tables presenting crash data disaggregated by gender or sex of the involved party.

2. Search **LTO (Land Transportation Office)** crash statistics databases for gender-based breakdowns.

3. Search **PSA (Philippine Statistics Authority)** for road crash mortality data by sex and age group.

4. Search **PhilHealth / DOH (Department of Health)** for trauma or injury registry data that includes gender.

5. Search **WHO Global Status Report on Road Safety** — Philippines country data (may include gender-disaggregated fatality estimates).

6. If only **national-level gender data** exists, document it as a possible proxy variable and note limitations.

---

### Gap 3 — Road-Segment-Level Crash Frequency

> **Priority: 🟠 HIGH — Required for Random Forest Hotspot model**

#### What Is Missing

A dataset recording the **number of crashes per named road, highway, or corridor** in Metro Manila. Only city/district-level aggregate counts currently exist. The `AADT_ML.csv` file has traffic volume per road segment but **no matching crash frequency** data at the segment level.

Target roads include: EDSA, C5, Marcos Highway, Commonwealth Ave, Aurora Blvd, Quezon Ave, MacArthur Highway, and other major Metro Manila corridors.

#### Why It Matters

The **Random Forest hotspot risk classification model** requires a dependent variable (crash count or crash rate) at the road/segment level to build meaningful risk predictions. City/district-level aggregation is **too coarse** for spatial hotspot prediction — two segments in the same city can have vastly different risk profiles.

#### Search Instructions

1. Search **MMDA road safety database** and MMDA Traffic Management reports for road-segment crash counts along major corridors.

2. Search **DPWH Road Safety Data Management System (RSDMS)** — DPWH may maintain segment-level crash databases not publicly exposed in MMARAS reports.

3. Search **NCTS (National Center for Transportation Studies, UP Diliman)** publications and technical reports for road segment crash data.

4. Search **data.gov.ph** for geospatial or road-segment-level crash frequency datasets (keywords: "road segment crashes", "corridor crash", "EDSA accident data").

5. Search **published Metro Manila road safety hotspot studies** for data tables that include per-road crash counts.

---

### Gap 4 — Supplementary / Verification Sources

> **Priority: 🟡 MEDIUM — Useful but not blocking primary models**

#### What Is Missing

Additional open datasets or APIs for **cross-validation or GIS enrichment**, including real-time/historical crash location data, international benchmarks, and enriched road network geometries.

#### Search Instructions

1. Search **MMDA Open Data API / Traffic Dashboard** for crash records with GPS coordinates or road-level location data.

2. Search **LTO Philippine Road Crash Reporting System (RRCRS)** for any open access crash records.

3. Search **World Bank Global Road Safety Facility** for Philippines-specific datasets or reports.

4. Search **iREAD (Integrated Road Accident Database)** under DPWH for any accessible records.

5. Search **OpenStreetMap** and **HOTOSM** for Metro Manila road network data usable as GIS base layers.

6. Search **PhilGIS / NAMRIA** for official administrative boundary shapefiles (barangay and city level).

---

## Section 4: Required Output Format

For every data source identified, record the following structured information:

| Field | Description |
|-------|-------------|
| **Source Name** | Name of the dataset or report |
| **Publishing Agency** | Government body, institution, or organization |
| **Years of Coverage** | Date range covered by the data |
| **Geographic Scope** | Metro Manila / National / City-level |
| **Data Format** | CSV, XLSX, PDF table, API, Shapefile, etc. |
| **Access Level** | Public / Request required / Restricted / Paywalled |
| **Direct Link or Location** | URL or document reference (page number) |
| **Relevance to Gap** | Gap 1 / Gap 2 / Gap 3 / Gap 4 |
| **Notes / Caveats** | Limitations, completeness, proxy suitability |

---

## Section 5: Methodological Workarounds (If Data Is Unavailable)

If public data cannot be found for a given gap, use the following fallback strategies:

### Gap 1 — Causation Data Unavailable

**Proxy strategy:** Use **collision type + vehicle type + time of day** as proxy independent variables for the Logistic Regression model.
- Rationale: Collision type (rear-end, head-on) and vehicle type (motorcycle) are correlated with human error causation categories.
- Limitation: The model will measure *association* with severity, not causal mechanism.
- Acknowledge in methodology: "Causation data was unavailable from public sources; collision type and vehicle type are used as behavioral proxies."
- Precedent: Several Philippine crash studies (Pinca et al., 2019; Regidor et al., 2011) use collision type as a causation proxy.

### Gap 2 — Gender Data Unavailable

**Proxy strategy:** Use **age bracket + vehicle type + time of day** combination as additional demographic predictors.
- Rationale: Age and vehicle type together provide partial demographic profiling.
- Limitation: Without sex, the model cannot differentiate risk by gender — a standard global road safety variable.
- Acknowledge in methodology: "Gender-disaggregated data was not available in Philippine MMARAS records; findings may underrepresent sex-based risk differentials."
- Precedent: WHO (2023) notes the Philippines lacks sex-disaggregated crash data at the sub-national level.

### Gap 3 — Road-Segment Crash Frequency Unavailable

**Proxy strategy:** Apply **Kernel Density Estimation (KDE)** on city-level crash counts to estimate spatial crash intensity at the road-segment level.
- Method: Use city crash centroids + road network geometry (from OpenStreetMap) to distribute city-level crashes proportionally by road length and AADT.
- Limitation: KDE-derived segment values are modeled estimates, not observed counts.
- Acknowledge in methodology: "Road-segment crash frequency was not available; KDE spatial disaggregation from city-level data is used as a spatial proxy."
- Precedent: Xie & Yan (2008) — "Kernel Density Estimation of Traffic Accidents in a Network Space"; Bíl et al. (2013) — application to Czech road network.

### Gap 4 — Supplementary Sources Unavailable

**Proxy strategy:** Use existing Metro Manila shapefiles + OpenStreetMap road network data for GIS enrichment without additional crash records.
- Limitation: Cross-validation will rely on held-out MMARAS data only.

---

## Section 6: Search Scope — Domains and Sources to Cover

### Philippine Government Sources

| Source | URL | Relevance |
|--------|-----|-----------|
| Philippine Open Data | [data.gov.ph](https://data.gov.ph) | Gaps 1, 3, 4 |
| MMDA | [mmda.gov.ph](http://mmda.gov.ph) | Gaps 1, 3, 4 |
| DPWH | [dpwh.gov.ph](http://dpwh.gov.ph) | Gap 3 |
| LTO | [lto.gov.ph](http://lto.gov.ph) | Gaps 2, 4 |
| PSA | [psa.gov.ph](https://psa.gov.ph) | Gap 2 |
| DOH | [doh.gov.ph](https://doh.gov.ph) | Gap 2 |
| DOTr | [dotc.gov.ph](http://dotc.gov.ph) | Gap 4 |

### Academic Sources

| Source | URL | Relevance |
|--------|-----|-----------|
| NCTS (UP Diliman) | [ncts.up.edu.ph](http://ncts.up.edu.ph) | Gaps 1, 3 |
| DLSU Research | [research.dlsu.edu.ph](http://research.dlsu.edu.ph) | Gaps 1, 2 |
| UP Diliman | [upd.edu.ph](http://upd.edu.ph) | Gaps 1, 3 |
| Mapua University | [mapua.edu.ph](http://mapua.edu.ph) | Gap 1 |
| Google Scholar | [scholar.google.com](https://scholar.google.com) | All gaps |
| ResearchGate | [researchgate.net](https://researchgate.net) | All gaps |

### International Sources

| Source | URL | Relevance |
|--------|-----|-----------|
| WHO Road Safety | [who.int/roadsafety](https://www.who.int/teams/social-determinants-of-health/safety-and-mobility/road-safety) | Gap 2 |
| World Bank GRSF | [worldbank.org](https://www.worldbank.org/en/topic/transport/brief/global-road-safety-facility) | Gaps 2, 4 |
| ADB | [adb.org](https://www.adb.org) | Gaps 2, 4 |
| OECD IRTAD | [stats.oecd.org/irtad](https://stats.oecd.org/Index.aspx?DataSetCode=IRTAD_ACCIDENTS) | Gap 2 |

### GIS Sources

| Source | URL | Relevance |
|--------|-----|-----------|
| PhilGIS | [philgis.org](http://philgis.org) | Gap 4 |
| NAMRIA | [namria.gov.ph](http://namria.gov.ph) | Gap 4 |
| HOTOSM Philippines | [hotosm.org](https://www.hotosm.org) | Gap 4 |
| OpenStreetMap Overpass API | [overpass-api.de](https://overpass-api.de) | Gaps 3, 4 |

---

## Section 7: Research Priority Order

| Priority | Gap | Blocking Which Model | Urgency |
|----------|-----|---------------------|---------|
| **1 — 🔴 CRITICAL** | Causation / Contributing Factors | Logistic Regression (Demographic Risk Profiling) | **Project cannot proceed without this** |
| **2 — 🟠 HIGH** | Road-Segment Crash Frequency | Random Forest (Hotspot Risk Prediction) | **Required for spatial risk model** |
| **3 — 🟠 HIGH** | Gender-Disaggregated Data | Logistic Regression (Demographic Risk Profiling) | **Improves model accuracy significantly** |
| **4 — 🟡 MEDIUM** | Supplementary / Verification Sources | Cross-validation and GIS enrichment | **Useful but not blocking primary models** |

---

*This document should be updated as data sources are found or ruled out. Record all findings in the output format table in Section 4 and update `reports/project_status.md` accordingly.*
