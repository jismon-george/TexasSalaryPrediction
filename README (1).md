# 🏛️ PRCP-1024 · Texas State Government Salary Prediction

> End-to-end Data Science project — EDA, Predictive Modelling & Payroll Analytics for all 113 Texas State Agencies

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python)
![Jupyter](https://img.shields.io/badge/Notebook-Jupyter-orange?logo=jupyter)
![scikit-learn](https://img.shields.io/badge/ML-scikit--learn-green?logo=scikit-learn)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

---

## 📌 Project Overview

The Texas Tribune obtained salary records from the **Texas State Comptroller** for every position across **113 state agencies**, made available under the *Texas Public Information Act*.

This project covers three core tasks:

| Task | Description |
|------|-------------|
| **Task 1** | Complete Exploratory Data Analysis (EDA) report |
| **Task 2** | Predictive model for employee annual salary / payroll |
| **Task 3** | Outlier analysis, manager–employee wage disparity, temporal trends |

---

## 📂 Repository Structure

```
PRCP-1024-TexasSalaryPrediction/
│
├── PRCP_1024_Texas_Salary_Prediction.ipynb   ← Main notebook (all tasks)
├── README.md                                 ← This file
├── requirements.txt                          ← Python dependencies
│
└── plots/                                    ← Auto-generated visualisations
    ├── plot_target_distribution.png
    ├── plot_categorical_distributions.png
    ├── plot_top_agencies.png
    ├── plot_salary_by_gender.png
    ├── plot_salary_by_ethnicity.png
    ├── plot_correlation_heatmap.png
    ├── plot_top_job_titles.png
    ├── plot_salary_outliers_boxplot.png
    ├── plot_wage_disparity.png
    ├── plot_temporal_trends.png
    ├── plot_model_comparison.png
    ├── plot_best_model_predictions.png
    └── plot_feature_importance.png
```

---

## 📊 Dataset

| Attribute | Description |
|-----------|-------------|
| `Agency` | Agency code |
| `Agency Name` | Full agency name |
| `Last Name / First Name / MI` | Employee identity |
| `Class Title` | Job title / role |
| `Ethnicity` | Employee ethnicity |
| `Gender` | Employee gender |
| `Status` | Employment status |
| `Employ Date` | Date of joining |
| `Hourly Rate` | Hourly pay rate |
| `Hrs per Week` | Weekly hours |
| `Monthly` | Monthly income |
| `Annual` | Annual income *(target variable)* |
| `State Number` | State employee ID |

**Source:** [Download Dataset](https://d3ilbtxij3aepc.cloudfront.net/projects/CDS-Capstone-Projects/salary.zip)

> The notebook auto-downloads and extracts the dataset on first run — no manual steps needed.

---

## 🔍 Key Findings

### Task 1 — EDA
- Dataset spans **113 Texas state agencies** with diverse demographics
- Annual income is **heavily right-skewed** — senior executives are outliers
- **Gender pay gap** observed — male employees earn a higher median salary
- Top agencies by headcount: Health & Human Services, TxDOT, Corrections

### Task 3 — Insights
- **Outliers (IQR method):** ~2–5% of employees earn > 1.5× IQR above Q3; mostly legitimate executive salaries
- **Biggest wage disparities:** Finance, Legal & Executive-branch agencies show 200–400% manager-to-employee pay gaps
- **Temporal:** Government headcount grew steadily through 2010, plateaued post-2015; nominal salaries have increased

---

## 🤖 Models Compared

| Model | R² | RMSE | MAE |
|-------|----|------|-----|
| Random Forest | ✅ Best | Low | Low |
| Extra Trees | High | Low | Low |
| Gradient Boosting | High | Medium | Medium |
| Decision Tree | Medium | Medium | Medium |
| Ridge Regression | Baseline | High | High |
| Lasso Regression | Baseline | High | High |
| Linear Regression | Baseline | High | High |
| K-Nearest Neighbours | Medium | Medium | Medium |

> **✅ Recommended for production:** Random Forest Regressor — best R², robust to outliers, interpretable via feature importance

---

## 🚀 How to Run

### 1. Clone the repository
```bash
git clone https://github.com/YOUR_USERNAME/PRCP-1024-TexasSalaryPrediction.git
cd PRCP-1024-TexasSalaryPrediction
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Launch Jupyter Notebook
```bash
jupyter notebook PRCP_1024_Texas_Salary_Prediction.ipynb
```

> **The notebook will automatically download and extract the dataset on the first run.** No manual data download required.

---

## 🛠️ Tech Stack

- **Python 3.8+**
- **pandas, numpy** — data manipulation
- **matplotlib, seaborn** — visualisation
- **scikit-learn** — machine learning models & evaluation
- **scipy** — statistical analysis

---

## 📋 Challenges & Solutions

| Challenge | Technique Used | Reason |
|-----------|---------------|--------|
| Missing values in numeric columns | Median imputation | Robust to outliers |
| High-cardinality categoricals (agency, job title) | Frequency encoding | Avoids feature explosion |
| Skewed target distribution | Tree-based models (scale-invariant) | Unaffected by skew |
| Salary outliers (executives) | IQR + Z-score analysis; retained for trees | Real signal, not noise |
| Null annual income when hourly data exists | Derived: `hourly × hrs/wk × 52` | Recovers otherwise-dropped rows |
| Mixed date formats | `pd.to_datetime(infer_datetime_format=True, errors='coerce')` | Graceful multi-format handling |

---

## 👤 Author

**Your Name**
- GitHub: [@your_username](https://github.com/your_username)
- LinkedIn: [Your LinkedIn](https://linkedin.com/in/your_profile)

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

*Data sourced from the Texas Tribune / Texas Comptroller via the Texas Public Information Act.*
