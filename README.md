# ConnectaTel Customer Analytics & Segmentation

![Python](https://img.shields.io/badge/python-3.9+-blue.svg)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=flat\&logo=pandas\&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

## Overview

This project analyzes customer demographics and service consumption patterns for a telecommunications provider, ConnectaTel. The analysis combines customer profile information with usage records to identify customer segments, evaluate data quality, detect unusual consumption behaviors, and generate business recommendations aimed at improving customer value and commercial performance.

---

## Business Problem

Telecommunications companies rely on customer segmentation and usage analytics to optimize pricing strategies, improve customer retention, and increase revenue per user.

The objective of this project is to:

* Assess the quality and reliability of customer and usage datasets.
* Understand demographic and behavioral characteristics of the customer base.
* Identify high-value customer segments.
* Detect extreme usage patterns and potential business opportunities.
* Generate actionable recommendations for plan optimization and customer growth.

---

## Datasets

The project integrates three structured datasets:

### 1. plans.csv

Contains plan specifications and pricing information.

Main fields:

* plan_name
* monthly_fee
* included_minutes
* included_messages
* overage_charges

### 2. users.csv

Customer demographic and subscription information.

Main fields:

* user_id
* age
* city
* registration_date
* current_plan
* churn_status

### 3. usage.csv

Historical customer service usage records.

Main fields:

* user_id
* interaction_type
* date
* duration
* message_length

---

## Project Workflow

### 1. Data Quality Assessment

The following issues were identified and addressed:

* Sentinel values in age (-999).
* Invalid city values ("?").
* Future registration dates (year 2026).
* Missing timestamps in usage records.
* Structural missing values in duration and message length fields.

### 2. Data Cleaning

Data preparation included:

* Standardization of invalid values.
* Missing value treatment.
* Date validation and correction.
* Data type conversion.
* Consistency checks across datasets.

### 3. Exploratory Data Analysis (EDA)

Key analyses included:

* Customer demographic distribution.
* Plan distribution.
* Usage behavior patterns.
* Service consumption trends.
* Missing value analysis.

### 4. Outlier Detection

The Interquartile Range (IQR) method was used to identify unusually high consumption behavior.

Rather than removing these observations, they were retained because they represent legitimate customer behavior and may indicate high-value customers.

### 5. Customer Segmentation

Customers were segmented according to usage intensity:

* Low Usage
* Medium Usage
* High Usage

The segmentation provides a framework for targeted commercial actions and personalized plan offerings.

---

## Key Findings

* The customer base is predominantly composed of adults and senior users.
* Most customers exhibit moderate consumption patterns.
* A small group of high-consumption users represents a significant business opportunity.
* Data quality issues were limited and successfully remediated.
* Usage behavior appears to be a stronger segmentation factor than age.

---

## Business Recommendations

* Develop targeted upgrade campaigns for high-usage customers.
* Evaluate intermediate plans for medium-usage users approaching plan limits.
* Monitor extreme-usage customers individually.
* Improve automated validation processes to prevent future data-quality issues.
* Personalize marketing initiatives according to customer usage behavior.

---

## Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Jupyter Notebook

---

## Repository Structure

```text
ConnectaTel-Customer-Analytics/
│
├── data/
│   ├── plans.csv
│   ├── users.csv
│   └── usage.csv
│
├── notebooks/
│   └── connectatel_customer_analytics.ipynb
│
├── images/
│   └── visualizations/
│
├── README.md
│
└── requirements.txt
```

---

## Running the Project

### Option 1: Google Colab

1. Upload the notebook to Google Colab.
2. Upload the datasets into the Colab environment.
3. Update file paths if necessary.
4. Run all notebook cells sequentially.

### Option 2: Local Environment

Clone the repository:

```bash
git clone https://github.com/your-username/ConnectaTel-Customer-Analytics.git
cd ConnectaTel-Customer-Analytics
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Open:

```text
connectatel_customer_analytics.ipynb
```

and run all cells.

---

## Reproducibility Guide

To reproduce the analysis:

1. Download or clone the repository.
2. Place the datasets inside the `/data` folder.
3. Install project dependencies.
4. Execute the notebook from top to bottom.
5. Review generated visualizations and business insights.

The notebook is fully reproducible and includes all cleaning, transformation, analysis, and visualization steps required to generate the final results.
