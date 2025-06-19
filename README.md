# 🛡️ Phishing URL Detection

This project aims to use statistical methods and regression modeling to detect phishing websites. The dataset contains over 11,000 URLs and 87 attributes, allowing for a comprehensive analysis. Our focus was on regression and classification models using feature selection and rigorous data preprocessing to enhance accuracy and interpretability.

---

## 📄 Project Overview

We applied various data science techniques—such as forward/backward feature selection, generalized linear modeling, logistic regression, and statistical inference—to build models that predict website behavior and flag phishing attempts. The primary goals were:

- Predict **web traffic** using linear regression.
- Classify **website status** (Phishing/Legitimate) using logistic regression.

This analysis contributes toward the automation of phishing detection systems that support user safety and cybersecurity.

---

## 📁 Folder Structure
```plaintext
📁 Phishing-URL-Detection/
├── Project_Code.ipynb # All code for the project including data cleaning, processing and model creation and testing
└── README.md # This file
````
---
## 📊 Dataset

**Size:** 11,430 URLs  
**Attributes:** 87 features  
**Target Variables:**
- `Web_traffic` (for regression)
- `Status` (for classification; binary: phishing or legitimate)

**Feature Groups:**
- 56 syntactic/structural features (e.g., length, symbols)
- 24 content-based features
- 7 from external tools (e.g., Google Index, PageRank)

**Cleaning Steps:**
- Dropped columns with excessive imbalance or redundancy
- Reduced feature count to ~45
- Scaled numerical features and encoded categoricals
- Ensured no missing values remained
- Applied VIF to reduce multicollinearity

---

## 📈 Exploratory & Inferential Analysis

- **Visualizations:** Boxplots, histograms, and correlation heatmaps (thresholded at 0.85)
- **Summary Statistics:** Mean, median, st. dev, quartiles, CV, etc.
- **Inferential Stats:**
  - Chi-square tests between feature pairs
  - Confidence intervals for means
  - One-way and two-way ANOVA for predictor interaction effects

---

## 🧠 Model Building

### 🔹 Linear Regression
- Target: `Web_traffic`
- Applied forward and backward feature selection
- Used log transformation for skewed target
- Best model metrics:
  - RMSE: 3.8579
  - R²: 0.4976
- Indicates moderate ability to explain variance; underfitting due to domain mismatch

### 🔹 Logistic Regression
- Target: `Status` (Phishing/Legitimate)
- Removed multicollinear features using VIF
- Applied feature scaling
- Encoded target variable to binary (1 = Phishing, 0 = Legitimate)
- Final model accuracy: **92.9%**

## 🧪 Model Validation

- **Linear Regression:**
  - First model (forward/backward selection): R² = 0.3936
  - Second model (forward on full set): R² = 0.4976
  - Residuals showed heteroscedasticity → opportunities for better models

- **Logistic Regression:**
  - Achieved high accuracy with a clear majority of correct classifications
  - Minimal but non-negligible false negatives (missed phishing sites)
  - Interpretable and scalable for practical use

---

## 💬 Discussion & Conclusions

- **Best Model:** Logistic regression with accuracy of 92.9%
- **Challenges:**
  - High imbalance in certain predictors
  - Presence of extreme outliers
  - Selecting informative vs redundant features
- **Insights:**
  - Linear models underperformed due to domain mismatch (data not built for traffic prediction)
  - Logistic regression proved effective for classification of phishing threats
- **Future Recommendations:**
  - Explore advanced ML models (e.g., Random Forest, SVM)
  - Improve feature engineering
  - Integrate real-world data for stronger generalization

---
## 👥 Team

* **Mohammed Arfan Ameen**
* **Shahana Akter Rista**
* **Joshua Thomas**

---

