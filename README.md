# Loan Data Cleaning & Analysis Project  
**A Comprehensive Guide to Data Preprocessing and Exploratory Data Analysis (EDA)**

---

## 📌 Overview  
This repository presents a complete data cleaning and analysis workflow focused on loan applicant data. It addresses real-world data challenges such as missing values, duplicates, outliers, and categorical data encoding. The cleaned dataset is then analyzed through various statistical methods and visualizations to extract meaningful insights.

---

## 📂 Repository Structure  
loan-data-analysis/  
├── data/  
│   ├── raw_loan_data.csv          # Original dataset  
│   
├── notebooks/  
│   ├── Assignment_1_Exploration.ipynb  # Initial data exploration  
│   └── Assignment_2_Cleaning.ipynb     # Data cleaning & analysis  
├── .gitignore  
└── README.md                     # This file  


---

## 🎯 Objectives

### Data Cleaning
- Handle missing values via deletion, imputation, and forward/backward fill.
- Remove duplicate rows and redundant columns.
- Detect and treat outliers.

### Data Transformation
- Convert categorical features (e.g., `education`, `self_employed`) into numerical formats.

### Exploratory Data Analysis (EDA)
- Generate statistical summaries.
- Create visualizations: histograms, box plots, scatter plots.

### Documentation
- Provide reproducible, well-documented code for each step.
- Summarize findings for stakeholders.

---

## 🔧 Tools & Technologies

- **Python 3**
- Libraries:
  - `pandas` (Data manipulation)
  - `numpy` (Numerical operations)
  - `matplotlib` & `seaborn` (Visualization)
  - `scipy` (Outlier detection)
  - `scikit-learn` (Label encoding)
- **Jupyter Notebook** for interactive analysis

---

## 📝 Step-by-Step Workflow

### 1. Data Exploration (`Assignment_1_Exploration.ipynb`)
- Load and inspect dataset.
- Check data types, missing values, basic statistics.
- Visualize feature distributions (e.g., `income_annum`, `loan_amount`).

### 2. Data Cleaning (`Assignment_2_Cleaning.ipynb`)

**Handle Duplicates:**  
```python
df.drop_duplicates(inplace=True)  # Remove duplicate rows

---
Impute Missing Values:

python
Copy
Edit
df['income_annum'].fillna(df['income_annum'].median(), inplace=True)
Remove Outliers:

python
Copy
Edit
from scipy import stats
z_scores = stats.zscore(df.select_dtypes(include='number'))
df = df[(z_scores < 3).all(axis=1)]
Encode Categorical Data:

python
Copy
Edit
from sklearn.preprocessing import LabelEncoder
df['education_encoded'] = LabelEncoder().fit_transform(df['education'])
---
## **3. Analysis & Visualization**
Correlation Matrix:

python
Copy

sns.heatmap(df.corr(), annot=True)
Box Plot for Outlier Detection:

python
Copy

sns.boxplot(data=df, x='loan_amount')
📊 Key Findings
Missing Values:
~5% of income_annum values were missing and replaced with the median.

Outliers:
~3% of loan_amount entries were detected as outliers and removed using Z-score method.

Categorical Data:
Categorical features like education and self_employed were label-encoded for modeling.

Correlations:
Strong positive correlation observed between income_annum and loan_amount.

🚀 How to Use This Repository
Clone the repository:

## **bash**
Copy:

  git clone https://github.com/your-username/loan-data-analysis.git
---
## **Install dependencies:**

### **bash**
Copy:
  
  pip install pandas numpy matplotlib seaborn scipy scikit-learn
---
### Run notebooks:

Open Assignment_1_Exploration.ipynb for initial data exploration.

Open Assignment_2_Cleaning.ipynb for data preprocessing and cleaning.

## **📜 License:** 
This project is licensed under the MIT License. See LICENSE for details.

# **📧 Contact**
For questions or collaborations, feel free to reach out:

HanaNajih

LinkedIn: Hana Najih
