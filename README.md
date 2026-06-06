# 💰 Texas State Government Salary Prediction

## 📌 Project Title

**Texas State Government Salary Prediction Using Machine Learning**

---

# 📖 Introduction

Government agencies generate large amounts of employee compensation data across different departments, positions, job categories, and employment levels. Analyzing salary datasets can help identify compensation trends, understand workforce structures, and build predictive models for estimating employee salaries.

This project focuses on predicting salaries of Texas State Government employees using Data Science and Machine Learning techniques. The project includes data preprocessing, exploratory data analysis (EDA), feature engineering, model development, evaluation, and salary prediction.

Using Python and Machine Learning algorithms, the project transforms raw salary records into predictive insights that can support workforce analytics and compensation planning.

---

# 🎯 Project Objectives

## Primary Objectives

- Analyze Texas State Government employee salary data.
- Clean and preprocess salary datasets.
- Identify factors influencing employee compensation.
- Build machine learning models for salary prediction.
- Evaluate model performance using standard metrics.
- Generate visual insights from salary distributions and trends.

## Secondary Objectives

- Explore relationships between job roles and salaries.
- Identify salary trends across departments.
- Improve prediction accuracy through feature engineering.
- Demonstrate a complete machine learning workflow.

---

# 🛠 Technology Stack

## Programming Language

- Python 3.x

---

## Libraries Used

### Data Processing

```python
import pandas as pd
import numpy as np
```

### Data Visualization

```python
import matplotlib.pyplot as plt
import seaborn as sns
```

### Machine Learning

```python
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import LabelEncoder
from sklearn.metrics import mean_absolute_error
from sklearn.metrics import mean_squared_error
from sklearn.metrics import r2_score
```

### Machine Learning Models

```python
from sklearn.linear_model import LinearRegression
from sklearn.ensemble import RandomForestRegressor
```

---

# 📂 Repository Structure

```text
TexasSalaryPrediction/
│
├── PRCP_1024_Texas_Salary_Prediction.ipynb
├── README.md
├── requirements.txt
├── .gitignore
└── files.zip
```

---

# 📊 Dataset Description

The dataset contains salary information for Texas State Government employees.

Typical features include:

| Feature | Description |
|----------|-------------|
| Employee Name | Employee identifier |
| Department | Government department |
| Position Title | Employee designation |
| Salary | Annual salary |
| Employment Type | Job category |
| Agency | Government agency |
| Experience | Years of service |
| Classification | Employee classification |

---

# 🏗 Project Workflow

```text
Data Collection
        ↓
Data Loading
        ↓
Data Cleaning
        ↓
Exploratory Data Analysis
        ↓
Feature Engineering
        ↓
Data Preprocessing
        ↓
Train-Test Split
        ↓
Machine Learning Model
        ↓
Model Evaluation
        ↓
Salary Prediction
```

---

# ⚙ Working of the Project

## Step 1: Import Required Libraries

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

### Purpose

Load required libraries for data analysis and machine learning.

---

## Step 2: Load Dataset

```python
df = pd.read_csv("Texas_Salary_Data.csv")
```

### Purpose

Read the salary dataset into a Pandas DataFrame.

---

## Step 3: Data Exploration

```python
df.head()

df.info()

df.describe()
```

### Purpose

- Understand dataset structure
- Check missing values
- Examine feature distributions
- Generate statistical summaries

---

## Step 4: Data Cleaning

```python
df.isnull().sum()
```

```python
df.dropna(inplace=True)
```

### Purpose

- Remove missing values
- Improve data quality
- Prepare data for modeling

---

## Step 5: Feature Engineering

Categorical variables are converted into numerical representations.

```python
from sklearn.preprocessing import LabelEncoder

encoder = LabelEncoder()

df["Department"] = encoder.fit_transform(df["Department"])
```

### Purpose

Machine learning algorithms require numerical inputs.

---

## Step 6: Feature Selection

```python
X = df.drop("Salary", axis=1)

y = df["Salary"]
```

### Purpose

Separate independent and dependent variables.

---

## Step 7: Train-Test Split

```python
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=42
)
```

### Purpose

Split dataset into training and testing sets.

---

## Step 8: Model Training

### Linear Regression

```python
from sklearn.linear_model import LinearRegression

model = LinearRegression()

model.fit(X_train, y_train)
```

### Random Forest Regressor

```python
from sklearn.ensemble import RandomForestRegressor

rf = RandomForestRegressor()

rf.fit(X_train, y_train)
```

### Purpose

Train predictive models on historical salary data.

---

## Step 9: Salary Prediction

```python
predictions = model.predict(X_test)
```

### Purpose

Predict salaries for unseen employee records.

---

## Step 10: Model Evaluation

### Mean Absolute Error (MAE)

```python
mae = mean_absolute_error(y_test, predictions)
```

### Mean Squared Error (MSE)

```python
mse = mean_squared_error(y_test, predictions)
```

### R² Score

```python
r2 = r2_score(y_test, predictions)
```

### Purpose

Evaluate prediction accuracy and model performance.

---

# 📊 Exploratory Data Analysis (EDA)

The project performs EDA to understand salary patterns.

---

## Salary Distribution Analysis

### Visualization

Histogram

### Purpose

Analyze:

- Salary spread
- Salary concentration
- High-income groups
- Outliers

### Insights

- Most employees fall within mid-range salary bands.
- High-salary employees form a smaller portion of the workforce.
- Salary distribution may be right-skewed.

---

## Department-wise Salary Analysis

### Visualization

Bar Chart

### Purpose

Compare average salaries across departments.

### Insights

- Certain departments offer significantly higher salaries.
- Technical and specialized roles often command higher compensation.

---

## Position-wise Salary Analysis

### Visualization

Box Plot

### Purpose

Compare salary ranges across job positions.

### Insights

- Management roles generally have higher salary ranges.
- Entry-level positions show lower compensation bands.

---

## Correlation Analysis

### Visualization

Correlation Heatmap

### Purpose

Identify relationships between variables affecting salary.

### Example Factors

- Experience
- Department
- Job Category
- Position Level

---

# 🤖 Machine Learning Models

## Linear Regression

### Description

A statistical algorithm that models relationships between dependent and independent variables.

### Advantages

- Simple
- Fast
- Easy to interpret

### Limitations

- Assumes linear relationships

---

## Random Forest Regressor

### Description

An ensemble learning algorithm that combines multiple decision trees.

### Advantages

- Higher prediction accuracy
- Handles non-linear relationships
- Reduces overfitting

### Limitations

- More computationally intensive

---

# 📈 Model Evaluation Metrics

## Mean Absolute Error (MAE)

Measures average prediction error.

Formula:

```text
MAE = Σ|Actual - Predicted| / n
```

---

## Mean Squared Error (MSE)

Measures squared prediction error.

Formula:

```text
MSE = Σ(Actual - Predicted)² / n
```

---

## R² Score

Measures model goodness of fit.

Formula:

```text
R² = 1 - (RSS / TSS)
```

Interpretation:

| Score | Performance |
|---------|-------------|
| 1.0 | Perfect |
| >0.8 | Excellent |
| 0.6–0.8 | Good |
| <0.5 | Needs Improvement |

---

# 🔍 Key Findings

### 1. Salary Prediction is Feasible

Machine learning models can effectively estimate employee salaries based on historical records.

### 2. Position and Department Influence Compensation

Job role and department significantly affect salary levels.

### 3. Experience Matters

Employees with greater experience generally earn higher salaries.

### 4. Data Quality Impacts Accuracy

Proper preprocessing improves predictive performance.

### 5. Random Forest Often Performs Better

Random Forest models typically outperform simple linear models for salary prediction tasks.

---

# 💡 Business Applications

The project can support:

- Workforce Planning
- Compensation Benchmarking
- Budget Forecasting
- HR Analytics
- Salary Structure Analysis
- Government Workforce Insights

---

# ✅ Conclusion

The Texas State Government Salary Prediction project demonstrates a complete Data Science and Machine Learning workflow for predicting employee compensation.

The project successfully:

- Cleans and preprocesses salary data.
- Performs exploratory data analysis.
- Identifies salary-driving factors.
- Builds predictive machine learning models.
- Evaluates model performance using industry-standard metrics.
- Generates actionable workforce analytics insights.

This project showcases practical applications of Data Science, Machine Learning, Data Analytics, and Predictive Modeling in public-sector workforce analysis.

---

# 🚀 Future Enhancements

## Machine Learning Improvements

- XGBoost Regressor
- Gradient Boosting
- Hyperparameter Tuning
- Ensemble Models

## Deployment

- Streamlit Web Application
- Flask API
- Interactive Dashboard

## Advanced Analytics

- Salary Trend Forecasting
- Employee Segmentation
- Compensation Optimization
- Explainable AI (XAI)

---

# 🛠 Installation

Clone the repository:

```bash
git clone https://github.com/jismon-george/TexasSalaryPrediction.git
cd TexasSalaryPrediction
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

# ▶️ Run the Project

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Open:

```text
PRCP_1024_Texas_Salary_Prediction.ipynb
```

Run all cells to perform:

- Data Cleaning
- EDA
- Feature Engineering
- Model Training
- Salary Prediction
- Model Evaluation

---

# 👨‍💻 Author

**JISMON GEORGE**

### Data Analyst | AI & Machine Learning Engineer

Skills Applied:

- Python
- Pandas
- NumPy
- Machine Learning
- Data Cleaning
- Exploratory Data Analysis
- Data Visualization
- Statistical Analysis
- Predictive Modeling

