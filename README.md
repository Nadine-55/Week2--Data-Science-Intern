# Heart Disease Prediction : Feature Engineering & Data Preprocessing

Data preprocessing pipeline built for AnalystLab Africa's Data Science Internship Programme, Week 2. This project transforms a raw clinical dataset into a machine-learning-ready dataset for predicting heart disease, with every preprocessing decision documented.

## Dataset

Heart Failure Prediction Dataset

- Source: [Kaggle](https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction)

- Records: 918 patients

- Columns: 12

- Target variable: HeartDisease (1 = disease present, 0 = absent)

## Business Questions

1. Which features are most relevant to the prediction problem?

2. Which variables require encoding?

3. Which variables require scaling or normalization?

4. Are there any redundant or highly correlated features?

5. How should missing values and outliers be handled?

6. What preprocessing techniques improve dataset quality?

7. Is the dataset ready for machine learning?

## Methods

- Data inspection with Pandas (structure, types, missing values, duplicates, descriptive statistics)

- Missing value detection, including disguised missing values encoded as 0 in RestingBP and Cholesterol

- Median imputation for missing clinical measurements

- Feature engineering: column renaming, AgeGroup binning

- Label Encoding for binary variables (Sex, ExerciseAngina)

- One-Hot Encoding for multi-category variables (ChestPainType, RestingECGResult, ST_Slope, AgeGroup)

- StandardScaler applied to continuous numeric features

- Outlier detection using IQR method, validated with Z-score

- Outlier treatment via capping (Winsorizing), preserving all patient records

- Feature selection using correlation analysis and a correlation heatmap

## Key Findings

- 172 of 918 records (19%) had a Cholesterol value of 0, identified as disguised missing data rather than a true reading

- Strongest predictors of heart disease: ST_Slope, ExerciseAngina, Oldpeak, MaxHeartRate, ChestPainType

- Age and AgeGroup were found to be redundant (correlation 0.70); AgeGroup dummy columns were removed

- Cholesterol showed weak correlation with the target despite being a well-known clinical risk factor

## Preprocessing Result

| Raw dataset | 918 x 12 |

| Cleaned dataset | 918 x 12, 0 missing values |

| ML-ready dataset | 918 x 16, fully numeric |
