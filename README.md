# ConnectaTel Customer Analytics & Segmentation

[![Python](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=flat&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

## Overview

This project analyzes customer demographics and service consumption patterns for a telecommunications provider, ConnectaTel. The analysis combines customer profile information with usage records to identify customer segments, evaluate data quality, detect unusual consumption behaviors, and generate business recommendations aimed at improving customer value and commercial performance.

> **Note:** the underlying datasets are not included in this repository. The notebook is provided with all outputs (tables, charts, and results) already generated, so the full analysis can be reviewed without re-running the code.

---

## Business Problem

Telecommunications companies rely on customer segmentation and usage analytics to optimize pricing strategies, improve customer retention, and increase revenue per user.

The objective of this project is to:

- Assess the quality and reliability of customer and usage datasets.
- Understand demographic and behavioral characteristics of the customer base.
- Identify high-value customer segments.
- Detect extreme usage patterns and potential business opportunities.
- Generate actionable recommendations for plan optimization and customer growth.

---

## Datasets

The project integrates three structured datasets (not included in this repository — see note above):

### 1. plans.csv
Contains plan specifications and pricing information.

Main fields: `plan_name`, `monthly_fee`, `included_minutes`, `included_messages`, `overage_charges`

### 2. users.csv
Customer demographic and subscription information.

Main fields: `user_id`, `age`, `city`, `registration_date`, `current_plan`, `churn_status`

### 3. usage.csv
Historical customer service usage records.

Main fields: `user_id`, `interaction_type`, `date`, `duration`, `message_length`

---

## Project Workflow

### 1. Data Quality Assessment

The following issues were identified and addressed:
- Sentinel values in age (-999).
- Invalid city values ("?").
- Future registration dates (year 2026).
- Missing timestamps in usage records.
- Structural missing values in duration and message length fields.

### 2. Data Cleaning

Data preparation included:
- Standardization of invalid values.
- Missing value treatment.
- Date validation and correction.
- Data type conversion.
- Consistency checks across datasets.

### 3. Exploratory Data Analysis (EDA)

Key analyses included:
- Customer demographic distribution.
- Plan distribution.
- Usage behavior patterns.
- Service consumption trends.
- Missing value analysis.

### 4. Outlier Detection

The Interquartile Range (IQR) method was used to identify unusually high consumption behavior. Rather than removing these observations, they were retained because they represent legitimate customer behavior and may indicate high-value customers.

### 5. Customer Segmentation

Customers were segmented according to usage intensity: Low Usage, Medium Usage, High Usage. The segmentation provides a framework for targeted commercial actions and personalized plan offerings.

---

## Key Findings

- The customer base is predominantly composed of adults and senior users.
- Most customers exhibit moderate consumption patterns.
- A small group of high-consumption users represents a significant business opportunity.
- Data quality issues were limited and successfully remediated.
- Usage behavior appears to be a stronger segmentation factor than age.

---

## Business Recommendations

- Develop targeted upgrade campaigns for high-usage customers.
- Evaluate intermediate plans for medium-usage users approaching plan limits.
- Monitor extreme-usage customers individually.
- Improve automated validation processes to prevent future data-quality issues.
- Personalize marketing initiatives according to customer usage behavior.

---

## Technologies Used

Python · Pandas · NumPy · Matplotlib · Seaborn · Jupyter Notebook

---

## Repository Structure

```
ConnectaTel-Customer-Analytics-Segmentation/
│
├── notebooks/
│   └── connectatel_analysis.ipynb   (includes all outputs)
│
├── LICENSE
├── README.md
└── requirements.txt
```

---

## Reviewing the Analysis

The notebook (`notebooks/connectatel_analysis.ipynb`) includes all outputs already generated — tables, charts, and results are visible directly on GitHub without needing to run any code.

To re-run the analysis with your own data, the notebook expects three CSV files (`plans.csv`, `users.csv`, `usage.csv`) matching the schema described above, loaded from a local `/data` folder.

---

**Author:** William Andrés Bernal Sosa — [GitHub](https://github.com/williambernal-data) · [LinkedIn](https://www.linkedin.com/in/william-bernal-data)
