# ChildHealth Insights: Exploring Childhood Anemia in Nigeria

### Statistical Analysis and Machine Learning

[![Python](https://img.shields.io/badge/Python-3.x-blue)](https://www.python.org/)
[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange)](https://jupyter.org/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-Machine%20Learning-F7931E)](https://scikit-learn.org/)

> Exploring childhood anemia in Nigeria using statistical analysis and machine learning to examine socioeconomic, geographic and demographic patterns.

---

##  Project Overview

Childhood anemia is an important public health concern, but its distribution is not the same across all communities.

In this project, I used data from the **2024 Demographic and Health Survey (DHS)** to examine patterns of anemia among children in Nigeria.

The analysis combines **exploratory data analysis, statistical testing and machine learning** to investigate how anemia varies across socioeconomic, geographic and residential groups and whether selected characteristics can be used to predict individual anemia status.

---

## Research Question

**Which socioeconomic, geographic, demographic and selected behavioral factors are associated with childhood anemia in Nigeria, and can these factors reliably predict individual anemia status?**

---

##  Objectives

* Examine the observed prevalence of anemia among children with available anemia measurements.
* Compare anemia prevalence across household wealth groups.
* Examine geographic and urban/rural differences in anemia.
* Assess associations between anemia and selected behavioral factors.
* Build and compare Logistic Regression and Random Forest classification models.
* Evaluate how well the selected variables predict individual anemia status.

---

##  Dataset

The analysis contains **27,783 child records**, of which **11,053 had available anemia measurements**.

For the main analysis, anemia was classified as:

* **Not anemic**
* **Anemic:** mild, moderate or severe

### Variables examined

* Geographic zone
* Household wealth index
* Urban/rural residence
* Recent fever history
* Household bed-net ownership
* Child bed-net use
* Birth order

> **Note:** The analysis focuses on children with available anemia measurements. The observed prevalence should therefore not automatically be interpreted as a national prevalence estimate for all children in the dataset.

---

#  Key Findings

## 1. Anemia varied across wealth groups

Among children with available anemia measurements, observed anemia prevalence ranged from **41.1% in the richest group to 50.9% in the poorer group**.

The association between wealth group and anemia status was statistically significant (**p < 0.001**).

![Anemia prevalence by wealth](reports/figures/anemia_by_wealth.png)

---

## 2. Geographic differences were observed

Observed anemia prevalence varied across geographic zones.

The **South East recorded the highest observed prevalence at 54.0%**, while North Central recorded 43.6%.

The association between geographic zone and anemia was statistically significant (**p < 0.001**).

![Anemia prevalence by geographic zone](reports/figures/anemia_by_zone.png)

---

## 3. Rural children had higher observed prevalence

Observed anemia prevalence was:

| Residence | Prevalence |
| --------- | ---------: |
| Urban     |      45.2% |
| Rural     |      49.4% |

![Urban vs rural anemia prevalence](reports/figures/anemia_urban_rural.png)

---

#  Machine Learning

Two classification models were compared:

* **Logistic Regression**
* **Random Forest**

| Model               | Accuracy | ROC-AUC |
| ------------------- | -------: | ------: |
| Logistic Regression |     ~54% |   0.559 |
| Random Forest       |     ~54% |   0.566 |

![ROC curve comparison](reports/figures/roc_comparison.png)

The models showed **limited predictive performance**.

This was an important finding: variables can show a statistical association with anemia at the population level without being strong enough to accurately predict anemia in individual children.

---

##  What Influenced the Random Forest Model?

The leading features included geographic zone, wealth category and birth order.

![Random Forest feature importance](reports/figures/feature_importance.png)

Feature importance indicates which variables contributed to the model's predictions; it does not establish causation.

---

#  What This Analysis Shows

The analysis points to three main observations:

**1. Socioeconomic differences exist.**
Anemia prevalence varied across household wealth groups.

**2. Geographic differences exist.**
Observed anemia prevalence differed across Nigeria's geographic zones.

**3. Association does not equal prediction.**
Although some variables were statistically associated with anemia, the machine learning models had limited ability to distinguish anemic from non-anemic children.

This highlights the importance of evaluating model performance rather than assuming that statistically significant variables will automatically produce useful predictions.

---

#  Methods

### Exploratory Analysis

* Descriptive statistics
* Cross-tabulation
* Data visualization
* Prevalence comparisons

### Statistical Analysis

* Chi-square tests of independence
* Significance level: α = 0.05

### Machine Learning

* One-hot encoding
* Stratified 80/20 train-test split
* Logistic Regression
* Random Forest Classifier

### Model Evaluation

* Accuracy
* Precision
* Recall
* F1-score
* Confusion matrix
* ROC-AUC
* Feature importance

---

#  Repository Structure

```text
childhealth-insights-nigeria-anemia/
│
├── README.md
│
├── data/
│   └── README.md
│
├── notebooks/
│   └── nigeria_childhood_anemia_analysis.ipynb
│
├── reports/
│   ├── research_report.md
│   └── figures/
│       ├── anemia_by_wealth.png
│       ├── anemia_by_zone.png
│       ├── anemia_urban_rural.png
│       ├── roc_comparison.png
│       └── feature_importance.png
│
├── src/
│   ├── preprocessing.py
│   ├── analysis.py
│   └── modeling.py
│
├── requirements.txt
├── LICENSE
└── .gitignore
```

---

#  Research Report

A detailed research report accompanying this analysis is available in:

`reports/research_report.md`

The report presents the study background, methodology, findings, interpretation and limitations in a research format.

---

# Limitations

* The analysis is observational and does not establish causality.
* The primary analysis was restricted to children with available anemia measurements.
* The selected predictors represent only a subset of factors that may influence childhood anemia.
* The machine learning models were evaluated using a single train-test split.
* No independent external validation dataset was used.
* DHS survey weights and the full complex survey design were not incorporated into this exploratory analysis.

---

#  Tools Used

**Python · Pandas · NumPy · SciPy · Matplotlib · Seaborn · Scikit-learn · Jupyter Notebook**

---

#  Future Work

Future analysis could explore:

* Additional demographic, nutritional and health-related predictors
* Multivariable logistic regression
* Anemia severity prediction
* Model calibration and cross-validation
* External validation using an independent dataset
* Appropriate DHS survey-weighted analysis

---

## Author

Juliet Oghenekevwe Ehwebayire**

Health Data Science | Data Analytics | Public Health

---

*This project was developed as an exploratory health data science analysis using DHS data.*

