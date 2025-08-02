Exploratory Data Analysis (EDA) is a crucial preliminary step before applying linear regression [NUMBER: 5 https://www.codecademy.com/learn/eda-exploratory-data-analysis-python]. It helps understand the data, identify relationships between variables, and ensure the suitability of using linear regression [NUMBER: 3 https://ksvmuralidhar.medium.com/basic-exploratory-data-analysis-template-for-regression-problems-20ca00c58f7d, NUMBER: 4 https://medium.com/@kaushalgupta198/exploratory-data-analysis-and-regression-8cc50c9bf51a].

Here's why EDA is important for linear regression:

Identify patterns and relationships: EDA techniques like visualizations can reveal linear relationships between the independent and dependent variables, which is a core assumption of linear regression [NUMBER: 2 https://blog.exploratory.io/introduction-to-linear-regression-model-in-exploratory-a46e90d62f7d, NUMBER: 4 https://medium.com/@kaushalgupta198/exploratory-data-analysis-and-regression-8cc50c9bf51a].
Check for outliers and anomalies: EDA can help detect outliers that can significantly affect the regression line and model [NUMBER: 5 https://www.codecademy.com/learn/eda-exploratory-data-analysis-python].
Identify potential issues: EDA can uncover data quality problems like missing values or skewed distributions, which might require pre-processing before using linear regression [NUMBER: 6 https://www.kaggle.com/code/jmullan/eda-and-linear-regression-prediction].
By performing EDA, you can ensure that your data meets the assumptions of linear regression and build a more accurate and reliable model [NUMBER: 1 https://www.analyticsvidhya.com/blog/2021/02/introduction-to-exploratory-data-analysis-eda/].

Sources
Analytics Vidhya: https://www.analyticsvidhya.com/blog/2020/10/exploratory-data-analysis-the-go-to-technique-to-explore-your-data/ - Get to know Your Data Using Exploratory Data Analysis
Blog of Exploratory: https://blog.exploratory.io/a-practical-guide-of-exploratory-data-analysis-with-linear-regression-part-1-9f3a182d7a92 - A Beginner's Guide to Exploratory Data Analysis with Linear Regression...
Medium - ksvmuralidhar: [invalid URL removed] - Basic Exploratory Data Analysis (EDA) template for regression problems...
Medium - Kaushal Gupta: https://medium.com/@kaushalgupta198/exploratory-data-analysis-and-regression-8cc50c9bf51a - EXPLORATORY DATA ANALYSIS AND REGRESSION
Codecademy: https://www.codecademy.com/article/eda-prior-to-fitting-a-regression-model - EDA Prior To Fitting a Regression Model
Kaggle: https://www.kaggle.com/code/jmullan/eda-and-linear-regression-prediction - EDA and Linear Regression Prediction

# USA-Accidents-Dataset Analysis 🚦
Exploratory Data Analysis of US Traffic Accidents (2016–2023)
Conducted a comprehensive exploratory analysis of the Kaggle US Accidents dataset representing 49 U.S. states with ~7.7 million records (Feb 2016–Mar 2023) 
Kaggle
Kaggle
. Utilized Python libraries (pandas, NumPy, seaborn, folium/base maps) to visualize spatiotemporal trends in accident frequency, severity, and environmental context. Built interpretable regression models (linear and media-type regression) to predict severity scores and validate insights. Published clean Jupyter notebooks and interactive visuals on GitHub with full documentation and reproducible methodology.



**Author:** _DragonGodMonarchMk_  
---

## 1. Project Overview

A data-analysis pipeline exploring a *U.S. nationwide traffic accident dataset* covering **February 2016 to March 2023** across **49 states**—capturing over **7.7 million** accidents :contentReference[oaicite:6]{index=6}. The analysis includes:

- Exploratory Data Analysis (EDA)
- Temporal and spatial trend visualization
- Statistical modeling to predict accident severity
- Demonstrating data-cleaning, model-building, and interactive map storytelling—all in Python.

This project aims to surface high-risk *times*, *locations*, and *conditions* for insights into road safety and incident prediction.

---

## 2. Dataset & Data Source

**US_Accidents_[March23].csv** (Kaggle ID: sobhanmoosavi/us-accidents)  
*Dataset description*:
- Aggregated from multiple APIs, including DOT/state agencies and traffic sensors.
- Key features: `Severity` (scale 1–4), `City`, `State`, `Start_Time`, `End_Time`, `Weather_Condition`, `Temperature(F)`, `Wind_Speed(mph)`, `Humidity(%)`, `Visibility(mi)`, `Sunrise_Sunset`, `Zipcode`, `TMC` (road segment), `Amenity`, etc. :contentReference[oaicite:7]{index=7}

The notebook workflow includes cleaning date-time formats, handling missing values, binning severity, and merging geographic & weather context.

---

## 3. Exploratory Data Analysis (EDA)

The core **`USA Accidents Analysis.ipynb`** notebook investigates:

- **Temporal patterns**: Hourly, weekly, monthly accident frequencies; highlight peaks around 3 PM–4 PM, Sundays/Mondays :contentReference[oaicite:8]{index=8}.
- **Geospatial insights**: Choropleth/density maps showing state/city-level accident hotspots.
- **Severity stratification**: Relation between weather, road features, time-of-day and accident severity.
- **Correlation exploration** between continuous variables (temp, wind speed, humidity, distance to hospital).

EDA is highlighted as a critical step *before* modeling to validate linear regression assumptions such as feature independence and outlier presence :contentReference[oaicite:9]{index=9}.

---

## 4. Predictive Modeling (Severity Regression)

To build a predictive baseline:

1. **Feature engineering**: One-hot encoding for categorical features (state, day-of-week), creation of derived features (duration, hour of day).
2. **Regression modeling**: Trained and evaluated **Linear Regression** (baseline) and **Random Forest Regressor** to predict **Severity** (1–4 scale).
3. **Validation**: Performed train/test split with temporal hold-out (latest 25% of incidents) and k-fold CV.
4. **Performance metrics**: Reported **R²**, **MAE**, and error distribution by severity class.

*(Example provisional scores: Linear R² ~ 0.45, MAE ~ 0.65; RF R² ~ 0.60, MAE ~ 0.50 — actual results depend on your run.)*

---

## 5. Hands-On Usage

### 📂 Structure
USA-Accidents-Dataset/
├── USA Accidents Analysis.ipynb ← principal EDA & modeling notebook
├── datasets/ ← raw data CSV (not committed if large)
├── maps/ ← saved map visualizations (PNG/HTML)
├── outputs/ ← charts, regression outputs
├── requirements.txt
└── README.md

6. Key Insights (Sample Findings)
🚘 Peak volume during weekday afternoons (3–4 PM) and early Sunday morning; lowest on Thursdays/Wednesdays 
LinkedIn
🌧️ Adverse weather (rain, fog, snow) significantly increases average severity.
🗺️ High-incident corridors observed in busy metro areas such as California, Texas, Florida, and New York.
⚠️ Severity score model achieved mid-range predictive power—highlighting scope for improvement via classification, clustering, or graph-based spatiotemporal models.

7. Future Extensions
Develop classification or forecasting models for incident prediction per region/time window.
Integrate external traffic or POI data, or use Graph Neural Networks for road-network-aware modeling 
arXiv
Create interactive dashboards with Plotly Dash or Streamlit.
Add driver/road safety indicators and causal inference analysis.

8. License & Acknowledgements
Dataset: US Accidents by Sobhan Moosavi et al., typically licensed under CC BY‑NC‑SA 4.0 (for research/academic use only) 
Sobhan Moosavi
arXiv
.

Code & Analysis: Released under MIT License (if you have included that file—otherwise default to same).

9. 🗣️ Contact & Contributions
Contributions are welcome via forks and pull requests.
Please cite appropriately if you use or reference this work, and feel free to open issues for clarifications or suggestions.

🧭 Final Tips
Populate project metrics and visual screenshots in your README to showcase results.
Highlight any map outputs (peak days/hours choropleths, severity overlay).
Add badges such as Python version, dataset size, license type to README header for polish.



