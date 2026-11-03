Cancer Data Analysis

An end-to-end data analysis project on 50,000 global cancer patient records (2015–2024). It uses Python for exploratory analysis, statistical testing and machine learning to understand what drives cancer severity, treatment cost and survival.

Overview

This project answers questions such as:

Which risk factors are most strongly linked to cancer severity?
How many cancers are diagnosed at an early stage, and does it vary by cancer type?
Does treatment cost differ across countries, genders and age groups?
Does higher treatment cost or a lower stage change survival?
Does genetic risk amplify the effect of smoking?

Key numbers: 50,000 patients | 10 countries | 8 cancer types | 15 columns | 0 missing values

Dataset
File: global_cancer_patients_2015_2024.csv
Size: 50,000 rows × 15 columns
Group	Columns
Patient	Patient_ID, Age, Gender, Country_Region, Year
Risk factors (0–10 scale)	Genetic_Risk, Air_Pollution, Alcohol_Use, Smoking, Obesity_Level
Diagnosis	Cancer_Type, Cancer_Stage
Outcomes	Treatment_Cost_USD, Survival_Years, Target_Severity_Score
Tools & Technologies
Purpose	Tools
Data handling	Python, Pandas, NumPy
Visualization	Matplotlib, Seaborn
Statistics	SciPy, Statsmodels
Machine learning	Scikit-learn (Random Forest, GridSearchCV)
Environment	Jupyter Notebook
Project Steps
Load and inspect: checked structure, data types, missing values and duplicates (none found).
Descriptive analysis: histograms, KDE plots, bar charts and pie charts for age, gender, country, cancer type, stage and cost.
Risk factor analysis: linear regression of each risk factor against the severity score.
Early-stage diagnosis: proportion of Stage 0 and Stage I cases by cancer type.
Predictor analysis: Pearson and Spearman correlations, plus Random Forest feature importance.
Economic burden: average cost by country, gender and age group (bar chart and heatmap).
Hypothesis testing:
Treatment cost vs. survival (Pearson, Spearman)
Cancer stage vs. cost and survival (Shapiro-Wilk, then Kruskal-Wallis)
Genetic risk × smoking interaction (OLS regression)
Key Results
Risk factors and severity
Factor	Correlation with severity	Regression R²
Smoking	0.48	0.23
Genetic Risk	0.48	0.23
Air Pollution	0.37	0.13
Alcohol Use	0.36	0.13
Obesity Level	0.25	0.06
Findings
Smoking and genetic risk are the strongest predictors of severity, followed by alcohol, air pollution and obesity.
The severity Random Forest reached a test R² of about 0.78 (train R² 0.97, so it shows some overfitting).
Survival is not predictable from the available features (test R² ≈ 0).
About 40% of cancers are diagnosed early, with lung cancer lowest (38.4%) and liver highest (40.6%).
Treatment cost is nearly uniform across countries (within about 2.5%), genders and age groups.
No significant link between treatment cost and survival (p = 0.92), or between cancer stage and cost (p = 0.43) or survival (p = 0.60).
No genetic risk × smoking interaction (p = 0.63). The two factors act independently.
Limitations
Most variables are evenly distributed and survival is unrelated to every other variable, which suggests the dataset may be simulated rather than real clinical data. Findings should not be read as medical conclusions.
Categorical variables were label-encoded, and the severity model overfits.
The dataset has no treatment type, comorbidity or follow-up information.
How to Run
1. Clone the repository
bash
git clone https://github.com/<your-username>/cancer-data-analysis.git
cd cancer-data-analysis
2. Install requirements
bash
pip install numpy pandas matplotlib seaborn scipy statsmodels scikit-learn jupyter
3. Run the notebook
bash
jupyter notebook

Open Cancer_Data_Analysis.ipynb and run all cells. Make sure the CSV path in the first cells matches the location of the file in the data/ folder.

Repository Structure
├── data/
│   └── global_cancer_patients_2015_2024.csv
├── notebooks/
│   └── Cancer_Data_Analysis.ipynb
├── report/
│   └── Cancer_Data_Analysis_Report.docx
├── images/
│   └── (chart screenshots)
└── README.md
Future Improvements
Cross-validation and feature selection to reduce overfitting
Gradient boosting models (XGBoost) and one-hot encoding
Survival analysis (Kaplan-Meier, Cox regression) on real clinical data
Interactive dashboard in Power BI or Streamlit
Author

Shravan Aldar,LinkedIn: https://www.linkedin.com/in/shravan-aldar-b72996301/  |  GitHub: https://github.com/shravax?tab=repositories
