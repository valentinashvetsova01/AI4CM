# Customer Analytics & Predictive Marketing

An end-to-end customer analytics project covering **segmentation, churn prediction, and customer lifetime value forecasting**. Each analysis moves from data cleaning and exploratory analysis to predictive modeling and actionable marketing recommendations.

## Project Overview

### 1. Customer Segmentation & Communication Strategy

Customer behavior was analyzed using **RFM segmentation** and **K-Means clustering** to identify distinct customer personas and define channel-specific communication strategies.

**Key results**
- Identified **3 actionable customer personas**
- **73% of revenue** comes from 40% of customers
- Catalog customers generate approximately **2.2× higher order value**
- 47% of customers browse frequently but convert poorly

**Methods:** data audit, feature engineering, RFM analysis, K-Means, PCA, silhouette analysis

[View notebook](./AI4CM_LabExam_Part1_%282%29.ipynb) · [View presentation](./AI4CM_LabExam_Part1_Presentation.pdf)

---

### 2. Customer Churn Prediction

Two classification models were developed to identify customers most likely to churn and support targeted retention campaigns.

**Best model: Random Forest**
- **97% accuracy**
- **0.93 recall** for churned customers
- **5.96× Lift@Top10%**

The strongest churn signals were:
- short customer tenure;
- low cashback;
- a recent complaint.

**Methods:** Logistic Regression, Random Forest, class balancing, confusion matrices, ROC-AUC, feature importance, lift analysis

[View notebook](./AI4CM_LabExam_Part2%20%282%29.ipynb) · [View presentation](./FINAL_CHURN_PRES.pdf)

---

### 3. Olist CLTV & Revenue Forecasting

Customer lifetime value and 90-day revenue were estimated using both a probabilistic approach and machine learning.

**Model comparison**

| Model | MAE | RMSE | Total forecast |
|---|---:|---:|---:|
| XGBoost | **1.65** | **16.99** | **67,582 BRL** |
| BG/NBD + Gamma-Gamma | 2.56 | 18.31 | 129,335 BRL |
| Actual holdout revenue | — | — | 66,727 BRL |

XGBoost produced a total forecast only **1.3% above the actual holdout revenue**.

The analysis also defines three marketing actions:
- win back high-value customers at risk;
- convert one-time buyers into repeat customers;
- protect the top active customer segment without unnecessary discounts.

**Methods:** RFM features, calibration/holdout validation, BG/NBD, Gamma-Gamma, XGBoost, CLTV scoring

[View notebook](./AI4CM_LabExam_Part3.ipynb) · [View presentation](./Olist_CLTV.pdf)

## Tech Stack

`Python` · `pandas` · `NumPy` · `Matplotlib` · `Seaborn` · `scikit-learn` · `XGBoost` · `Lifetimes` · `KaggleHub`

## Repository Structure

```text
.
├── AI4CM_LabExam_Part1_(2).ipynb
├── AI4CM_LabExam_Part1_Presentation.pdf
├── AI4CM_LabExam_Part2 (2).ipynb
├── FINAL_CHURN_PRES.pdf
├── AI4CM_LabExam_Part3.ipynb
└── Olist_CLTV.pdf
```

## Running the Notebooks

Install the required packages:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn openpyxl xgboost lifetimes kagglehub jupyter
```

Then open the notebooks in Jupyter or Google Colab.

- **Part 1** requires `marketing_campaign.csv`.
- **Part 2** requires `data.xlsx`, sheet `E Comm`.
- **Part 3** downloads the Brazilian E-Commerce Public Dataset by Olist through `kagglehub`.

Update the dataset paths in Parts 1 and 2 before running them outside the original Google Drive environment.
