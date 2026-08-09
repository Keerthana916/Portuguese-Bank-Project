# Portuguese Bank Marketing Prediction

 A machine learning classification project that predicts whether a bank customer will subscribe to a term deposit based on customer characteristics, previous campaign interactions, and economic indicators.

---

## Project Overview

The objective of this project is to develop a predictive model that helps a **bank marketing team identify customers who are more likely to subscribe to a term deposit**.

The project analyzes customer demographics, financial information, previous campaign outcomes, contact details, and economic indicators to identify patterns associated with term-deposit subscriptions.

---

## Business Objective

The main objective is to answer:

> **Which customers are more likely to subscribe to a term deposit?**

The predictive solution can help the marketing team:

* Identify potential customers
* Improve campaign targeting
* Reduce unnecessary customer contacts
* Focus marketing efforts on higher-probability customers
* Make data-driven campaign decisions

---

## Dataset

The project uses the **Portuguese Bank Marketing dataset**.

The dataset contains customer information, campaign-related variables, previous contact information, and economic indicators.

### Target Variable

* `yes` → Customer subscribed to a term deposit
* `no` → Customer did not subscribe

---

## Key Features

| Feature          | Description                            |
| ---------------- | -------------------------------------- |
| `age`            | Age of the customer                    |
| `job`            | Type of occupation                     |
| `marital`        | Marital status                         |
| `education`      | Education level                        |
| `default`        | Credit default status                  |
| `housing`        | Housing loan status                    |
| `loan`           | Personal loan status                   |
| `contact`        | Communication type                     |
| `month`          | Month of last contact                  |
| `day_of_week`    | Day of last contact                    |
| `duration`       | Duration of the last contact           |
| `campaign`       | Number of contacts during the campaign |
| `pdays`          | Days since previous campaign contact   |
| `previous`       | Number of previous contacts            |
| `poutcome`       | Previous campaign outcome              |
| `emp.var.rate`   | Employment variation rate              |
| `cons.price.idx` | Consumer price index                   |
| `cons.conf.idx`  | Consumer confidence index              |
| `euribor3m`      | 3-month Euribor rate                   |
| `nr.employed`    | Number of employees                    |

---

## Exploratory Data Analysis

The project performs univariate and bivariate analysis to understand customer behavior and campaign performance.

### Analysis includes:

* Customer age distribution
* Campaign contact distribution
* Customer job and subscription relationship
* Marital status and subscription behavior
* Education and subscription behavior
* Housing loan and subscription behavior
* Personal loan and subscription behavior
* Contact duration and subscription
* Campaign frequency and subscription
* Previous campaign outcome
* Economic indicators
* Correlation analysis

---

## Key Insights

### Customer Profile

* Retired, student, and unemployed customers showed relatively higher subscription proportions.
* Blue-collar and service-sector customers had comparatively lower subscription rates.
* Single customers showed a higher proportion of subscriptions compared with married customers.

### Education

Customers with professional courses and high-school education showed comparatively better subscription rates.

### 💳 Loans

Customers without personal loans appeared more likely to subscribe to the term deposit.

### Campaign Interaction

Customers who subscribed generally had **longer contact durations**, suggesting that successful engagement may be associated with longer interactions.

However, increasing the number of campaign contacts did not necessarily result in more subscriptions.

---

## Data Preprocessing

The preprocessing workflow includes:

* Missing-value checking
* Duplicate detection and removal
* Categorical variable encoding
* Outlier detection
* Outlier treatment
* Feature correlation analysis
* Train-test splitting
* Class balancing using SMOTE

### Class Imbalance

The target variable was highly imbalanced.

Before SMOTE:

```text
Class 0 → 29,272
Class 1 →  3,668
```

After SMOTE:

```text
Class 0 → 29,272
Class 1 → 29,272
```

SMOTE was applied to the training data to balance the target classes.

---

## Feature Analysis

Correlation analysis identified strong relationships among several economic indicators.

Notable correlations included:

* `emp.var.rate` ↔ `euribor3m`
* `euribor3m` ↔ `nr.employed`

These variables represent different aspects of the broader economic environment and showed strong positive relationships in the dataset.

---

## 🤖 Machine Learning Models

The project compares several classification algorithms:

* Logistic Regression
* K-Nearest Neighbors (KNN)
* Support Vector Machine (SVM)
* Decision Tree
* Random Forest
* Gradient Boosting
* XGBoost

---

## Model Evaluation

Models were evaluated using:

* Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix
* Classification Report

### Model Performance

| Model               | Accuracy | F1-score |
| ------------------- | -------: | -------: |
| Logistic Regression |      83% |     0.53 |
| KNN                 |      83% |     0.53 |
| SVM                 |      78% |     0.43 |
| Decision Tree       |      88% |     0.52 |
| Random Forest       |      90% |     0.59 |
| Gradient Boosting   |      90% |     0.59 |
| XGBoost             |      90% |     0.60 |

> **XGBoost and Random Forest performed best overall according to the project's model comparison, with XGBoost achieving an F1-score of 0.60.**

---

## Challenges

### Class Imbalance

The dataset contained significantly more customers who did not subscribe than customers who subscribed.

**Solution:** SMOTE was applied to balance the training data.

### Feature Correlation

Several economic variables were strongly correlated.

**Approach:** Correlation analysis was performed to understand relationships and support feature selection.

### Interpretability vs Performance

Logistic Regression provides better interpretability, while ensemble models such as Random Forest and XGBoost provided stronger predictive performance.

---

## Marketing Recommendations

Based on the analysis:

* Prioritize customers in the **30–60 age range**, along with potentially responsive groups such as students, retirees, and entrepreneurs.
* Consider **cellular communication** as the primary contact method.
* Focus campaigns during **March, October, and December** based on the project analysis.
* Avoid excessive campaign contacts when there are no positive engagement signals.
* Monitor economic indicators such as **Euribor rates** when planning campaigns.

---

## Technologies Used

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**
* **Scikit-learn**
* **XGBoost**
* **Imbalanced-learn**
* **Jupyter Notebook**

