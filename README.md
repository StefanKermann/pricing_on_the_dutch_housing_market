# Pricing Drivers in the Dutch Housing Market: A WOZ-Based Structural Analysis

## Executive Summary
This project delivers a data-driven macroeconomic analysis of municipal-level price formation across the Dutch residential real estate market, with a strategic focus on the **Randstad** region. Using advanced statistical modeling, it dissects the dominance of the statutory valuation system (*Waardering onroerende zaken* — WOZ) and exposes the divergent market mechanics between single-family houses (EGW) and multi-family/institutional properties (MGW).

**Key Business Insight:** The analysis proves that EGW and MGW segments follow completely different market logics—EGW being highly heterogeneous and micro-location-driven, while MGW behaves as a standardized, institutional, and stable asset class heavily tethered to regulatory frameworks. 

---

## Technical Stack & Workflow Architecture
To mirror professional data engineering environments, this project avoids monolithic code and is strictly structured into **chronological, production-ready Jupyter Notebooks**. 

* **Languages & Core Libraries:** Python, Pandas, NumPy, Scikit-Learn (Linear Regression), Statsmodels, Seaborn, Matplotlib, SciPy.
* **Methodology:** Ordinary Least Squares (OLS) Regression, LOESS (Local Regression) Trend Analysis, Strict Residual Diagnostics, Boxplot Volatility Analysis.
* **Data Origin:** Centraal Bureau voor de Statistiek (CBS) — integrated across ~30 regional macro-economic and structural datasets.

---

## Repository Structure & Data Pipeline
The repository is systematically divided to ensure 100% clarity and scannability for recruiters and tech leads:

├── notebooks/ # Chronological Data Science Pipeline (01 to 10)
│ ├── 01_data_cleaning_cbs.ipynb # Initial structural reshaping of CBS source sheets
│ ├── 02_data_merging.ipynb # Spatial and economic data aggregation
│ ├── 03_exploratory_data_analysis.ipynb # Heatmaps, geographic distributions & collinearity checks
│ ├── 04_ols_baseline_modeling.ipynb # Establishing the baseline WOZ price predictor
│ ├── 05_residual_analysis.ipynb # Evaluating model fit and identifying structural anomalies
│ ├── 06_spatial_patterns_randstad.ipynb # Deep-dive into Randstad sub-market dynamics
│ ├── 07_egw_mgw_segmentation.ipynb # Uncovering segment-specific market variances
│ ├── 08_loess_nonlinear_modeling.ipynb # Capturing non-linear shifts (The "Banana" effect)
│ ├── 09_volatility_dispersion_plots.ipynb# Boxplot and spread modeling (Price-to-WOZ ratio)
│ └── 10_final_synthesis_diagnostics.ipynb# Model validation, limitations, and future scaling
├── plots/ # Exported high-resolution market visualizations
├── reports/ # Final management presentations & asset briefs
└── .gitignore # Local data security shield (excludes heavy raw Excel data)

---

## Strategic Real Estate Insights Uncovered

### 1. The Omnipresence of the WOZ Value
Baseline OLS models demonstrate that the WOZ-value acts as the single dominant price driver, yielding an exceptionally high model fit with an **$R^2$ ranging from 0.93 to 0.97**. Because the WOZ value is inherently transaction-based, it captures the vast majority of market variance, leaving traditional structural variables (income, population density) as minor localized adjusters.

### 2. The Non-Linear "Banana" Effect (Segment Divergence)
By plotting price deviations against the share of single-family housing (EGW-share), a distinct non-linear LOESS trend emerges (coined **"The Banana"**):
* **MGW-Dominated Markets (<50% EGW):** Exhibit tight alignment with statutory values or trade at a negative ratio to the model price, heavily influenced by institutional net-rent valuation logic and strict rental cap regulations.
* **EGW-Dominated Markets (>80% EGW):** Exhibit explosive, demand-driven price premiums that decouple from standard linear models, reflecting private market competition and emotional premium pricing.

### 3. Price Level vs. Price Dispersion
While an increase in EGW-share does not statistically shift the *absolute price level* in standard log-linear models, it fundamentally alters **price dispersion**. Boxplot analytics confirm that EGW-dominated municipalities suffer from massively higher volatility and wider spreads, whereas institutional MGW markets remain highly concentrated and predictable.

### 4. The Randstad Anomaly
The Randstad remains the economic heart of the country, holding ~45% of the population on just 20% of the land area. This immense density triggers a vastly higher baseline of multi-family properties (30.9% MGW vs. 19.6% nationwide), accelerating institutional asset-management workflows and structured rental income pricing.

---

## Future Roadmap: Granular Scaling
As proven by residual clustering, municipal-level aggregation serves as an excellent macroeconomic baseline but obscures micro-market anomalies

© 2026 [Stefan Kermann]. All rights reserved.